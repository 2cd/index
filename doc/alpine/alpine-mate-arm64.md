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
tag = ["mate", "2022-03-17"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "alpine-mate_arm64_2022-03-17_00-23.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "94ac47f13f99d26687952a58d4eece39708e8848834352879a522f291c6e4afb"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1011M"
tar_bytes = 1059096576

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "320M"
zstd_bytes = 334497515

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220310"
previous_tag = "2022-03-10"
previous_file = "alpine-mate_arm64_2022-03-10_00-29-rootfs.tar.zst"
previous_sha256 = "816774461207f67fc00f9dc07e19a750632ea7ab8fd16918ea0cfeeea720865e"

current_version = "latest01"
current_date = "20220317"
old_file = "alpine-mate_arm64_2022-03-03_00-27-rootfs.tar.zst"
old_sha256 = "394f3b2c96f8d41d729acfc40709089df6bef8898158d8e2d696edf8bcdad033"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-mate_arm64_2022-03-17_00-23-rootfs.tar.zst
# SHA256SUM=94ac47f13f99d26687952a58d4eece39708e8848834352879a522f291c6e4afb
# BUILD_DATE=20220317
# BUILD_TAG=2022-03-17
# STATUS=completed
# VERSION=latest01
# END_TIME=00:23

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-17
begin = 2022-03-17 00:06:11.885247748+00:00
start-sync_0 = 00:19:55
start-zstd = 00:20:46
start-sync_1 = 00:23:30
end-sync_1 = 00:23:55
end = 2022-03-17 00:23:55.971275350+00:00

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
