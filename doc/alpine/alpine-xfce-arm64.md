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
tag = ["xfce", "2024-02-22"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_arm64_2024-02-22_00-24.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0e53e7d4f55602a63d472696692883f1578c42f286b2230ee4b6e01b6f5dbb59"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1342788608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "412M"
zstd_bytes = 431078821

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231123"
previous_tag = "2023-11-23"
previous_file = "alpine-xfce_arm64_2023-11-23_00-15-rootfs.tar.zst"
previous_sha256 = "a4e9a1c5c208f8809b1c235c01b41d285551fb045c3fe1ee6ea8d03703f4ce72"

current_version = "latest02"
current_date = "20240222"
old_file = "alpine-xfce_arm64_2023-11-16_00-15-rootfs.tar.zst"
old_sha256 = "4afb6b6dd05b4a3b0fe7608f81a0fbc30dd2ee7f24fa6759de208a035c57a824"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-xfce_arm64_2024-02-22_00-24-rootfs.tar.zst
# SHA256SUM=0e53e7d4f55602a63d472696692883f1578c42f286b2230ee4b6e01b6f5dbb59
# BUILD_DATE=20240222
# BUILD_TAG=2024-02-22
# STATUS=completed
# VERSION=latest02
# END_TIME=00:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-22
begin = 2024-02-22 00:09:16.810837592+00:00
start-sync_0 = 00:20:07
start-zstd = 00:20:53
start-sync_1 = 00:24:24
end-sync_1 = 00:24:47
end = 2024-02-22 00:24:47.189901586+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.4_git20230717'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
