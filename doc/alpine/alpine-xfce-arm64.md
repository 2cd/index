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

## alpine-xfce-arm64.toml

```toml
[main]
name = "alpine"
tag = ["xfce", "2022-09-01"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_arm64_2022-09-01_00-31.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "48b566fec74a5ff2d8a45452ee752fe07c68393726b4ed7f0fbd1483bc2ad67d"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "932M"
tar_bytes = 977226240

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "315M"
zstd_bytes = 329525813

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220825"
previous_tag = "2022-08-25"
previous_file = "alpine-xfce_arm64_2022-08-25_00-26-rootfs.tar.zst"
previous_sha256 = "9c49564ff481d515b573e1c2a909c0b2c4a52eeee2013ea4a7e9d3e67647faa9"

current_version = "latest02"
current_date = "20220901"
old_file = "alpine-xfce_arm64_2022-08-18_00-25-rootfs.tar.zst"
old_sha256 = "bd658d28c31a21b905ddcff7f2e4ae45a8c6f036ba3fbe64226ef1240ba26b2c"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-xfce_arm64_2022-09-01_00-31-rootfs.tar.zst
# SHA256SUM=48b566fec74a5ff2d8a45452ee752fe07c68393726b4ed7f0fbd1483bc2ad67d
# BUILD_DATE=20220901
# BUILD_TAG=2022-09-01
# STATUS=completed
# VERSION=latest02
# END_TIME=00:31

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-01
begin = 2022-09-01 00:07:03.406593806+00:00
start-sync_0 = 00:26:33
start-zstd = 00:27:29
start-sync_1 = 00:30:54
end-sync_1 = 00:31:30
end = 2022-09-01 00:31:30.336300223+00:00

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
