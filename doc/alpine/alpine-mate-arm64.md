# alpine-mate-arm64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
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
    --name alpine-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-mate-arm64 zsh
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

## alpine-mate-arm64.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2022-09-01"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_arm64_2022-09-01_00-25.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c8f73f6c93f4d4ce16687b839df9fd48934911763e4998f527a335782fe3e0c7"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1074616320

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "320M"
zstd_bytes = 335098430

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220825"
previous_tag = "2022-08-25"
previous_file = "alpine-mate_arm64_2022-08-25_00-25-rootfs.tar.zst"
previous_sha256 = "fd7782289f993a82475642d46818ff504bdcef3595c09f996afaa6d10cc152b3"

current_version = "latest02"
current_date = "20220901"
old_file = "alpine-mate_arm64_2022-08-18_00-28-rootfs.tar.zst"
old_sha256 = "f9cce78b4273fb73b1604a17e36a3a170075fb29ce7451f85d5e157e4dcbd67a"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-mate_arm64_2022-09-01_00-25-rootfs.tar.zst
# SHA256SUM=c8f73f6c93f4d4ce16687b839df9fd48934911763e4998f527a335782fe3e0c7
# BUILD_DATE=20220901
# BUILD_TAG=2022-09-01
# STATUS=completed
# VERSION=latest02
# END_TIME=00:25

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-01
begin = 2022-09-01 00:06:59.863328594+00:00
start-sync_0 = 00:20:46
start-zstd = 00:21:36
start-sync_1 = 00:24:52
end-sync_1 = 00:25:17
end = 2022-09-01 00:25:17.691343946+00:00

[server]
repo = "cake233/alpine-mate-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.3'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
