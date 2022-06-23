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
tag = ["xfce", "2022-06-23"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_arm64_2022-06-23_00-30.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2a1090ce2edafaeda1aad01e60d49dbd10c9a372662d84ddffdcd6cd7f906808"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "937M"
tar_bytes = 981780480

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "330M"
zstd_bytes = 345211336

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220616"
previous_tag = "2022-06-16"
previous_file = "alpine-xfce_arm64_2022-06-16_00-26-rootfs.tar.zst"
previous_sha256 = "04e0322e7cf54237335565804eaa8d865d388ea4ae648a5475539bc0db8cbafa"

current_version = "latest02"
current_date = "20220623"
old_file = "alpine-xfce_arm64_2022-06-09_00-26-rootfs.tar.zst"
old_sha256 = "c4c33d8c27e4f601d3bcca35be87b9a9495f5f19f00602bf8cdf9ecb44f8ed70"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-xfce_arm64_2022-06-23_00-30-rootfs.tar.zst
# SHA256SUM=2a1090ce2edafaeda1aad01e60d49dbd10c9a372662d84ddffdcd6cd7f906808
# BUILD_DATE=20220623
# BUILD_TAG=2022-06-23
# STATUS=completed
# VERSION=latest02
# END_TIME=00:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-23
begin = 2022-06-23 00:06:38.999269520+00:00
start-sync_0 = 00:25:05
start-zstd = 00:26:07
start-sync_1 = 00:29:47
end-sync_1 = 00:30:20
end = 2022-06-23 00:30:20.878845086+00:00

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
zsh = 'zsh 5.8.1 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
