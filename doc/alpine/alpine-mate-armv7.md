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

```
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
tag = ["mate", "2022-05-19"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_armhf_2022-05-19_00-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9f0411c09082850ac333d48fec0ddad64af1f4db1bc3f9e5a52b158c8a5e774f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "671M"
tar_bytes = 703124992

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "228M"
zstd_bytes = 238635894

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220512"
previous_tag = "2022-05-12"
previous_file = "alpine-mate_armhf_2022-05-12_00-12-rootfs.tar.zst"
previous_sha256 = "907c758eb83d5acb9e1135dced21e85b0760624bcb228d2815cf6c02d5739f16"

current_version = "latest02"
current_date = "20220519"
old_file = "alpine-mate_armhf_2022-05-05_00-47-rootfs.tar.zst"
old_sha256 = "0cc45f2b2848ae2a4d85ee484c1a0db19fa152d73ecda40bdb790c0825c052a1"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-mate_armhf_2022-05-19_00-11-rootfs.tar.zst
# SHA256SUM=9f0411c09082850ac333d48fec0ddad64af1f4db1bc3f9e5a52b158c8a5e774f
# BUILD_DATE=20220519
# BUILD_TAG=2022-05-19
# STATUS=completed
# VERSION=latest02
# END_TIME=00:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-19
begin = 2022-05-19 00:06:38.773314021+00:00
start-sync_0 = 00:08:23
start-zstd = 00:08:58
start-sync_1 = 00:11:22
end-sync_1 = 00:11:42
end = 2022-05-19 00:11:42.335997779+00:00

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
current = true
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = true
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
ldd = 'musl libc (armhf) Version 1.2.3'
zsh = 'zsh 5.8.1 (armv7-alpine-linux-musleabihf)'

[port]
tcp = [5902, 36080]
```
