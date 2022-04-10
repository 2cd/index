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
tag = ["mate", "2022-04-10"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "alpine-mate_armhf_2022-04-10_09-02.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "871578e6816badc4c0434309f7941ec359ae30bcc36fd58716ce5c3bb48733ac"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "695M"
tar_bytes = 728123392

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "235M"
zstd_bytes = 245545034

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220406"
previous_tag = "2022-04-06"
previous_file = "alpine-mate_armhf_2022-04-06_23-11-rootfs.tar.zst"
previous_sha256 = "663444980d897fcc788641af7c7d9867078d376df04f36bddf628ffb4443d80e"

current_version = "latest02"
current_date = "20220410"
old_file = "alpine-mate_armhf_2022-03-30_23-11-rootfs.tar.zst"
old_sha256 = "b786af30b786cf5f0c013fa1280027d66c6498216c5685c03cf84dce6a6a3c59"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-mate_armhf_2022-04-10_09-02-rootfs.tar.zst
# SHA256SUM=871578e6816badc4c0434309f7941ec359ae30bcc36fd58716ce5c3bb48733ac
# BUILD_DATE=20220410
# BUILD_TAG=2022-04-10
# STATUS=completed
# VERSION=latest02
# END_TIME=09:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-10
begin = 2022-04-10 08:57:16.884387053+00:00
start-sync_0 = 08:59:17
start-zstd = 08:59:56
start-sync_1 = 09:01:58
end-sync_1 = 09:02:20
end = 2022-04-10 09:02:20.139059646+00:00

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
ldd = 'musl libc (armhf) Version 1.2.3'
zsh = 'zsh 5.8.1 (armv7-alpine-linux-musleabihf)'

[port]
tcp = [5902, 36080]
```
