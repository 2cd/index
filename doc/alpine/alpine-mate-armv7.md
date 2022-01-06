# alpine-mate-armv7

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not armv7, then install qemu & binfmt-support.
    apt install qemu-user-static
fi

# 5903 is the host vnc port
# 5902 is the container vnc port
# 36080 is the container novnc port
docker run \
    -it \
    --shm-size 512m \
    -p 5903:5902 \
    -p 36081:36080 \
    --name alpine-mate-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-mate-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-mate-armv7 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```sh
    startvnc
```

or

```sh
    startx11vnc
```

or

```sh
    novnc
```

Note:

If you want to use novnc, then open your browser, and type the address:

```
http://localhost:36081
```

If you want to use tiger/x11vnc, then open vnc viewer, then type the address:

```
localhost:5903
```

## alpine-mate-armv7.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2022-01-06"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "alpine-mate_armhf_2022-01-06_00-28.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "9567fab33379e1a09b328ede68461ea2a80e1b8a481fe96f6cd4b0dc2a131f3a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "708M"
tar_bytes = 741630976

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "236M"
zstd_bytes = 246663365

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211230"
previous_tag = "2021-12-30"
previous_file = "alpine-mate_armhf_2021-12-30_00-29-rootfs.tar.zst"
previous_sha256 = "7f0478ceccadb4d008970139d43aaa2cfa05039bbf1ccfcbdabc880706c6310f"

current_version = "latest02"
current_date = "20220106"
old_file = "alpine-mate_armhf_2021-12-23_00-31-rootfs.tar.zst"
old_sha256 = "840684645c094a2476b3a356a4fc14a39389c6fd36bb5b274d58b6fd3258ed0c"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-mate_armhf_2022-01-06_00-28-rootfs.tar.zst
# SHA256SUM=9567fab33379e1a09b328ede68461ea2a80e1b8a481fe96f6cd4b0dc2a131f3a
# BUILD_DATE=20220106
# BUILD_TAG=2022-01-06
# STATUS=completed
# VERSION=latest02
# END_TIME=00:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-06
begin = 2022-01-06 00:06:43.902359253+00:00
start-sync_0 = 00:25:00
start-zstd = 00:25:48
start-sync_1 = 00:28:11
end-sync_1 = 00:28:39
end = 2022-01-06 00:28:39.229581347+00:00

[server]
repo = "cake233/alpine-mate-armv7"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
previous = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (armhf) Version 1.2.2'
zsh = 'zsh 5.8 (armv7-alpine-linux-musleabihf)'

[port]
tcp = [5902, 36080]
```
