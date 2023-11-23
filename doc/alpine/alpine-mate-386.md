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
tag = ["mate", "2023-11-23"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_i386_2023-11-23_00-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6684af2d8bbc96750d080a39c8995ced15b844c3ef04584d3197a68370a085ee"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "706M"
tar_bytes = 739703296

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "232M"
zstd_bytes = 242481194

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231116"
previous_tag = "2023-11-16"
previous_file = "alpine-mate_i386_2023-11-16_00-11-rootfs.tar.zst"
previous_sha256 = "64e18cdf74976daf12a21e7f732e0c64086fe9b4c61af0037b714f11cee37996"

current_version = "latest01"
current_date = "20231123"
old_file = "alpine-mate_i386_2023-11-09_00-13-rootfs.tar.zst"
old_sha256 = "d6ee9dcddc2f97576bb34c0d2e37c76e0392281d9b7cc3ea670a7bc3f43e6785"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-mate_i386_2023-11-23_00-12-rootfs.tar.zst
# SHA256SUM=6684af2d8bbc96750d080a39c8995ced15b844c3ef04584d3197a68370a085ee
# BUILD_DATE=20231123
# BUILD_TAG=2023-11-23
# STATUS=completed
# VERSION=latest01
# END_TIME=00:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-23
begin = 2023-11-23 00:07:41.171838772+00:00
start-sync_0 = 00:10:30
start-zstd = 00:10:57
start-sync_1 = 00:12:39
end-sync_1 = 00:12:55
end = 2023-11-23 00:12:55.053284035+00:00

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
ldd = 'musl libc (i386) Version 1.2.4_git20230717'
zsh = 'zsh 5.9 (i586-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
