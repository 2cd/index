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
tag = ["xfce", "2022-06-16"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_amd64_2022-06-16_00-15.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "73fbb2986476579fd8c8784db133a7d5e31948116dd9f6f31ee416e50d1f939d"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "914M"
tar_bytes = 957986304

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "287M"
zstd_bytes = 300300341

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220609"
previous_tag = "2022-06-09"
previous_file = "alpine-xfce_amd64_2022-06-09_00-14-rootfs.tar.zst"
previous_sha256 = "a93d9d13f65a94b1467e5d15fb599d49f34adafbce21a3fc268134cfaae032ba"

current_version = "latest01"
current_date = "20220616"
old_file = "alpine-xfce_amd64_2022-06-02_00-13-rootfs.tar.zst"
old_sha256 = "11f88375d2d23a80a988adfe174c614f6ad4632e0c3778ef526be1cf4573e338"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-xfce_amd64_2022-06-16_00-15-rootfs.tar.zst
# SHA256SUM=73fbb2986476579fd8c8784db133a7d5e31948116dd9f6f31ee416e50d1f939d
# BUILD_DATE=20220616
# BUILD_TAG=2022-06-16
# STATUS=completed
# VERSION=latest01
# END_TIME=00:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-16
begin = 2022-06-16 00:07:05.331033941+00:00
start-sync_0 = 00:11:06
start-zstd = 00:11:56
start-sync_1 = 00:15:12
end-sync_1 = 00:15:34
end = 2022-06-16 00:15:34.460968164+00:00

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
zsh = 'zsh 5.8.1 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
