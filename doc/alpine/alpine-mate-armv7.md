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
tag = ["mate", "2022-02-03"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "alpine-mate_armhf_2022-02-03_00-25.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "1643dac50720d050585f3a0975077e5cd6143bffe5b8fc8366b8ffe77bd4d095"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "711M"
tar_bytes = 745409024

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "237M"
zstd_bytes = 247822973

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220127"
previous_tag = "2022-01-27"
previous_file = "alpine-mate_armhf_2022-01-27_00-24-rootfs.tar.zst"
previous_sha256 = "b3bb8d5147c2d1e608855edc4b8eb12ead7df0a456ab4f98777c1f36580bc280"

current_version = "latest01"
current_date = "20220203"
old_file = "alpine-mate_armhf_2022-01-20_00-25-rootfs.tar.zst"
old_sha256 = "7e32225383acb2977988c24dec8e4a6999acfe6b6f46ea928951b8505a013c39"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-mate_armhf_2022-02-03_00-25-rootfs.tar.zst
# SHA256SUM=1643dac50720d050585f3a0975077e5cd6143bffe5b8fc8366b8ffe77bd4d095
# BUILD_DATE=20220203
# BUILD_TAG=2022-02-03
# STATUS=completed
# VERSION=latest01
# END_TIME=00:25

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-03
begin = 2022-02-03 00:06:31.811154506+00:00
start-sync_0 = 00:22:03
start-zstd = 00:22:43
start-sync_1 = 00:24:51
end-sync_1 = 00:25:20
end = 2022-02-03 00:25:20.952601805+00:00

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
