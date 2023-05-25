# alpine-mate-amd64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not amd64, then install qemu & binfmt-support.
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
    --name alpine-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-mate-amd64 zsh
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

## alpine-mate-amd64.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2023-05-25"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_amd64_2023-05-25_00-15.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6322f34dd43df357f5841699ec92228237da07c42a69b67409168861574e72bb"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1242291200

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "378M"
zstd_bytes = 396229329

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230518"
previous_tag = "2023-05-18"
previous_file = "alpine-mate_amd64_2023-05-18_00-14-rootfs.tar.zst"
previous_sha256 = "1756d7cfa42df23a4d082984b8ca308b080d511b9791ca482ff2727522405865"

current_version = "latest02"
current_date = "20230525"
old_file = "alpine-mate_amd64_2023-05-11_00-13-rootfs.tar.zst"
old_sha256 = "fb11ed7c129bd7151b8d70eafa42a5da5ec48e758884f9a44f0ead686d0b7cab"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-mate_amd64_2023-05-25_00-15-rootfs.tar.zst
# SHA256SUM=6322f34dd43df357f5841699ec92228237da07c42a69b67409168861574e72bb
# BUILD_DATE=20230525
# BUILD_TAG=2023-05-25
# STATUS=completed
# VERSION=latest02
# END_TIME=00:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-25
begin = 2023-05-25 00:06:55.477310925+00:00
start-sync_0 = 00:08:51
start-zstd = 00:10:00
start-sync_1 = 00:14:49
end-sync_1 = 00:15:20
end = 2023-05-25 00:15:20.239639870+00:00

[server]
repo = "cake233/alpine-mate-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.4'
zsh = 'zsh 5.9 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
