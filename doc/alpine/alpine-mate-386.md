# alpine-mate-386

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not 386, then install qemu & binfmt-support.
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
    --name alpine-mate-386 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-mate-386

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-mate-386 zsh
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

## alpine-mate-386.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2022-05-05"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_i386_2022-05-05_01-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "012f13622adaf9ed9a0a686c86762c4d5c17ebd8ba558adaf7602af5c935c589"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "797M"
tar_bytes = 834694656

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "251M"
zstd_bytes = 262702987

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220428"
previous_tag = "2022-04-28"
previous_file = "alpine-mate_i386_2022-04-28_00-33-rootfs.tar.zst"
previous_sha256 = "6a4e3fc8d7fb4abed2ad2edbb5a41b67a4ca6da767ece764d4962840cf5d9c8f"

current_version = "latest02"
current_date = "20220505"
old_file = "alpine-mate_i386_2022-04-21_00-28-rootfs.tar.zst"
old_sha256 = "7ca450fabd8d93b555fc6bf048a0fda35e58c7645a176431f7e360e0aca90667"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-mate_i386_2022-05-05_01-03-rootfs.tar.zst
# SHA256SUM=012f13622adaf9ed9a0a686c86762c4d5c17ebd8ba558adaf7602af5c935c589
# BUILD_DATE=20220505
# BUILD_TAG=2022-05-05
# STATUS=completed
# VERSION=latest02
# END_TIME=01:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-05
begin = 2022-05-05 00:42:45.310736243+00:00
start-sync_0 = 01:00:05
start-zstd = 01:00:49
start-sync_1 = 01:03:05
end-sync_1 = 01:03:27
end = 2022-05-05 01:03:27.795390767+00:00

[server]
repo = "cake233/alpine-mate-386"

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
ldd = 'musl libc (i386) Version 1.2.3'
zsh = 'zsh 5.8.1 (i586-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
