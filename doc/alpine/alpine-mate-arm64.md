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
tag = ["mate", "2022-04-06"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "alpine-mate_arm64_2022-04-06_23-25.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "7759d9ec6215eb1a3b8d3257d1a4fdd1d57d52d8336883072374b6f199e46ab3"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1010M"
tar_bytes = 1058968064

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "320M"
zstd_bytes = 335186645

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220330"
previous_tag = "2022-03-30"
previous_file = "alpine-mate_arm64_2022-03-30_23-32-rootfs.tar.zst"
previous_sha256 = "0845a6ee409fab0486a027bee374db15d8c86c19881dea670b4cdb85af587f14"

current_version = "latest02"
current_date = "20220406"
old_file = "alpine-mate_arm64_2022-03-24_00-31-rootfs.tar.zst"
old_sha256 = "f8861576672ef421f810e26a39c53f3b9c2d0ad01202774ee99ee8161ab29352"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-mate_arm64_2022-04-06_23-25-rootfs.tar.zst
# SHA256SUM=7759d9ec6215eb1a3b8d3257d1a4fdd1d57d52d8336883072374b6f199e46ab3
# BUILD_DATE=20220406
# BUILD_TAG=2022-04-06
# STATUS=completed
# VERSION=latest02
# END_TIME=23:25

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-06
begin = 2022-04-06 23:06:16.031403835+00:00
start-sync_0 = 23:21:10
start-zstd = 23:22:01
start-sync_1 = 23:25:13
end-sync_1 = 23:25:37
end = 2022-04-06 23:25:37.665278988+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.2'
zsh = 'zsh 5.8.1 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
