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
tag = ["kde", "2023-03-23"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-kde_arm64_2023-03-23_00-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4118a62520a98abcf185fee4203aa5b03ed36f17406364e2c30118f46ede62c3"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.9G"
tar_bytes = 1943475200

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "550M"
zstd_bytes = 576690559

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230316"
previous_tag = "2023-03-16"
previous_file = "alpine-kde_arm64_2023-03-16_00-24-rootfs.tar.zst"
previous_sha256 = "c20cd6a79b3759232b99e80cc3ec3f0b176a7230766999f0e4d91aa616df2c0d"

current_version = "latest02"
current_date = "20230323"
old_file = "alpine-kde_arm64_2023-03-09_00-22-rootfs.tar.zst"
old_sha256 = "2b89e81cd12d168a5eb21e39225a3486fd0e17288e110463e4972d7a710dd7fb"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-kde_arm64_2023-03-23_00-29-rootfs.tar.zst
# SHA256SUM=4118a62520a98abcf185fee4203aa5b03ed36f17406364e2c30118f46ede62c3
# BUILD_DATE=20230323
# BUILD_TAG=2023-03-23
# STATUS=completed
# VERSION=latest02
# END_TIME=00:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-23
begin = 2023-03-23 00:07:12.708479167+00:00
start-sync_0 = 00:19:46
start-zstd = 00:21:31
start-sync_1 = 00:28:46
end-sync_1 = 00:29:33
end = 2023-03-23 00:29:33.293660401+00:00

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
