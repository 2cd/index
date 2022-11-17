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
tag = ["xfce", "2022-11-17"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_arm64_2022-11-17_00-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "21effdbe83a49d1ea7a802e9c5aec81db6a2c5d369069b836e37d786080553f7"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "919M"
tar_bytes = 963537920

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "282M"
zstd_bytes = 294705715

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221110"
previous_tag = "2022-11-10"
previous_file = "alpine-xfce_arm64_2022-11-10_00-21-rootfs.tar.zst"
previous_sha256 = "3e487ab7d3e8b35f32a80330d34b300479d0631f5f751ce897a76e72d702d928"

current_version = "latest01"
current_date = "20221117"
old_file = "alpine-xfce_arm64_2022-11-03_00-20-rootfs.tar.zst"
old_sha256 = "5ed13c348227a3f55dace3aa5d5eda1d8cdd848c2afc4916cd4d096aaaad8052"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-xfce_arm64_2022-11-17_00-20-rootfs.tar.zst
# SHA256SUM=21effdbe83a49d1ea7a802e9c5aec81db6a2c5d369069b836e37d786080553f7
# BUILD_DATE=20221117
# BUILD_TAG=2022-11-17
# STATUS=completed
# VERSION=latest01
# END_TIME=00:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-17
begin = 2022-11-17 00:06:17.061802448+00:00
start-sync_0 = 00:15:52
start-zstd = 00:16:45
start-sync_1 = 00:19:39
end-sync_1 = 00:20:04
end = 2022-11-17 00:20:04.321927722+00:00

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
