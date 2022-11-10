# alpine-xfce-amd64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not amd64, then install qemu & binfmt-support.
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
    --name alpine-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-xfce-amd64 zsh
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

## alpine-xfce-amd64.toml

```toml
[main]
name = "alpine"
tag = ["xfce", "2022-11-10"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_amd64_2022-11-10_00-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1453154728651095cfb840bb7fcda9dd51facfe8b026b3c826c50eee0d776cce"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "954M"
tar_bytes = 999677440

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "327M"
zstd_bytes = 341915138

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221103"
previous_tag = "2022-11-03"
previous_file = "alpine-xfce_amd64_2022-11-03_00-13-rootfs.tar.zst"
previous_sha256 = "be342c435b2268de9cf8bf6c3ec9e4b5f071c6f26c3eaab33f5809b51dff2f3a"

current_version = "latest02"
current_date = "20221110"
old_file = "alpine-xfce_amd64_2022-10-27_00-13-rootfs.tar.zst"
old_sha256 = "64aabd0147953e517eabe307f649ca14469f6f3e268a0a37b1ed76975bd77a58"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-xfce_amd64_2022-11-10_00-13-rootfs.tar.zst
# SHA256SUM=1453154728651095cfb840bb7fcda9dd51facfe8b026b3c826c50eee0d776cce
# BUILD_DATE=20221110
# BUILD_TAG=2022-11-10
# STATUS=completed
# VERSION=latest02
# END_TIME=00:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-10
begin = 2022-11-10 00:07:29.886110432+00:00
start-sync_0 = 00:08:53
start-zstd = 00:09:46
start-sync_1 = 00:13:10
end-sync_1 = 00:13:36
end = 2022-11-10 00:13:36.394894224+00:00

[server]
repo = "cake233/alpine-xfce-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.3'
zsh = 'zsh 5.9 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
