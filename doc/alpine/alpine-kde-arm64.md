# alpine-kde-arm64

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
    --name alpine-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-kde-arm64 zsh
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

## alpine-kde-arm64.toml

```toml
[main]
name = "alpine"
tag = ["kde", "2022-11-20"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-kde_arm64_2022-11-20_21-21.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9dd4b211e1a831813e8f679b8d78a89d29b8907d9826d888ec23c5f241172687"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1884700160

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "514M"
zstd_bytes = 538847777

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221117"
previous_tag = "2022-11-17"
previous_file = "alpine-kde_arm64_2022-11-17_00-23-rootfs.tar.zst"
previous_sha256 = "3e50902663b2a8b2e65ef4cf28beb2ee9fedf58863fa112eae2570b7642efc9b"

current_version = "latest02"
current_date = "20221120"
old_file = "alpine-kde_arm64_2022-11-10_00-24-rootfs.tar.zst"
old_sha256 = "026a4291fcaf1e9c3ba0ef61d7d6b5176b8b2a9f4c3ff0427524cc9269064334"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-kde_arm64_2022-11-20_21-21-rootfs.tar.zst
# SHA256SUM=9dd4b211e1a831813e8f679b8d78a89d29b8907d9826d888ec23c5f241172687
# BUILD_DATE=20221120
# BUILD_TAG=2022-11-20
# STATUS=completed
# VERSION=latest02
# END_TIME=21:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-20
begin = 2022-11-20 21:03:34.026220159+00:00
start-sync_0 = 21:13:08
start-zstd = 21:14:38
start-sync_1 = 21:20:51
end-sync_1 = 21:21:26
end = 2022-11-20 21:21:26.354408929+00:00

[server]
repo = "cake233/alpine-kde-arm64"

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
