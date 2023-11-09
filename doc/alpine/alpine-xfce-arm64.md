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
tag = ["xfce", "2023-11-09"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_arm64_2023-11-09_00-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "26de948bd757e0a3d9fb4002b4b5a09e183093744eff3b5879ed6773e8edbc83"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "456M"
tar_bytes = 478034432

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "179M"
zstd_bytes = 186732171

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231026"
previous_tag = "2023-10-26"
previous_file = "alpine-xfce_arm64_2023-10-26_00-18-rootfs.tar.zst"
previous_sha256 = "196c84807ed7bd786d16cf135075e0c1ef4e81a564b7f256d0a7d91367d4767c"

current_version = "latest01"
current_date = "20231109"
old_file = "alpine-xfce_arm64_2023-10-19_00-17-rootfs.tar.zst"
old_sha256 = "e9db97e0c2e1f2dc1c02a3a04215c7f2b979844d1002d3dc5f15fee2e27b896c"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-xfce_arm64_2023-11-09_00-11-rootfs.tar.zst
# SHA256SUM=26de948bd757e0a3d9fb4002b4b5a09e183093744eff3b5879ed6773e8edbc83
# BUILD_DATE=20231109
# BUILD_TAG=2023-11-09
# STATUS=completed
# VERSION=latest01
# END_TIME=00:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-09
begin = 2023-11-09 00:07:33.577553258+00:00
start-sync_0 = 00:09:38
start-zstd = 00:09:57
start-sync_1 = 00:11:05
end-sync_1 = 00:11:23
end = 2023-11-09 00:11:23.887083031+00:00

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
