# alpine-xfce-arm64

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
    --name alpine-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-xfce-arm64 zsh
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

## alpine-xfce-arm64.toml

```toml
[main]
name = "alpine"
tag = ["xfce", "2022-01-27"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "alpine-xfce_arm64_2022-01-27_00-32.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "a0f347f904e61d12c14def37e2b117cd2df964f09867b11c53b7d3ca138ecdd0"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "862M"
tar_bytes = 903740416

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "314M"
zstd_bytes = 328454306

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220120"
previous_tag = "2022-01-20"
previous_file = "alpine-xfce_arm64_2022-01-20_00-30-rootfs.tar.zst"
previous_sha256 = "d3c699775d3c1f64d4330c7811788910fb078e64b52db57b132649437a899d7a"

current_version = "latest02"
current_date = "20220127"
old_file = "alpine-xfce_arm64_2022-01-13_00-34-rootfs.tar.zst"
old_sha256 = "1380fb6217da8e0becbf3013b6c19ecb1d01f477c1c6c74e220355e0c0dfe492"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-xfce_arm64_2022-01-27_00-32-rootfs.tar.zst
# SHA256SUM=a0f347f904e61d12c14def37e2b117cd2df964f09867b11c53b7d3ca138ecdd0
# BUILD_DATE=20220127
# BUILD_TAG=2022-01-27
# STATUS=completed
# VERSION=latest02
# END_TIME=00:32

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-27
begin = 2022-01-27 00:06:36.827809983+00:00
start-sync_0 = 00:27:41
start-zstd = 00:28:48
start-sync_1 = 00:31:58
end-sync_1 = 00:32:31
end = 2022-01-27 00:32:31.304905192+00:00

[server]
repo = "cake233/alpine-xfce-arm64"

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
zsh = 'zsh 5.8 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
