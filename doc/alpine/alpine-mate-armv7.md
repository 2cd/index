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
tag = ["mate", "2022-11-03"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_armhf_2022-11-03_00-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3396b49929a45c1bd25b40a221c22bcc07a86f9ba82c989cc837391c2a8b67a0"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "685M"
tar_bytes = 717309440

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "221M"
zstd_bytes = 231603647

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221027"
previous_tag = "2022-10-27"
previous_file = "alpine-mate_armhf_2022-10-27_00-12-rootfs.tar.zst"
previous_sha256 = "e42d25640c140b6c4d6c65fb6268041635112e8e2e3ccbc536a94bb3d1157dd1"

current_version = "latest02"
current_date = "20221103"
old_file = "alpine-mate_armhf_2022-10-20_00-11-rootfs.tar.zst"
old_sha256 = "47bcd08bc56c6562e5e16e4b4a351942295d759b29a2da9acd01bd194736f11a"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-mate_armhf_2022-11-03_00-11-rootfs.tar.zst
# SHA256SUM=3396b49929a45c1bd25b40a221c22bcc07a86f9ba82c989cc837391c2a8b67a0
# BUILD_DATE=20221103
# BUILD_TAG=2022-11-03
# STATUS=completed
# VERSION=latest02
# END_TIME=00:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-03
begin = 2022-11-03 00:06:55.510966058+00:00
start-sync_0 = 00:08:49
start-zstd = 00:09:22
start-sync_1 = 00:11:22
end-sync_1 = 00:11:41
end = 2022-11-03 00:11:41.695104701+00:00

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
zsh = 'zsh 5.9 (armv7-alpine-linux-musleabihf)'

[port]
tcp = [5902, 36080]
```
