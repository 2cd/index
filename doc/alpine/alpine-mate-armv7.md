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
tag = ["mate", "2022-11-17"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_armhf_2022-11-17_00-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "54aaded26c3a0e120cfbdd587e84d42a457871cdcb321b60f7ce3f911bfa4b55"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "686M"
tar_bytes = 718535168

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "221M"
zstd_bytes = 231492573

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221110"
previous_tag = "2022-11-10"
previous_file = "alpine-mate_armhf_2022-11-10_00-11-rootfs.tar.zst"
previous_sha256 = "e7ea4e6369b5e9611869b66b6e7243903e6aa5af2ca36ebb8b2caad242071379"

current_version = "latest02"
current_date = "20221117"
old_file = "alpine-mate_armhf_2022-11-03_00-11-rootfs.tar.zst"
old_sha256 = "3396b49929a45c1bd25b40a221c22bcc07a86f9ba82c989cc837391c2a8b67a0"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-mate_armhf_2022-11-17_00-11-rootfs.tar.zst
# SHA256SUM=54aaded26c3a0e120cfbdd587e84d42a457871cdcb321b60f7ce3f911bfa4b55
# BUILD_DATE=20221117
# BUILD_TAG=2022-11-17
# STATUS=completed
# VERSION=latest02
# END_TIME=00:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-17
begin = 2022-11-17 00:06:13.953317173+00:00
start-sync_0 = 00:08:20
start-zstd = 00:08:52
start-sync_1 = 00:10:41
end-sync_1 = 00:11:00
end = 2022-11-17 00:11:00.208935349+00:00

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
