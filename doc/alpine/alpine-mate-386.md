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
tag = ["mate", "2022-05-19"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_i386_2022-05-19_00-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "babfb001eed3db0977e770b7a020c5419f16f7633cc6148d3fc3ad2df32f0ff1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "770M"
tar_bytes = 807240192

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "244M"
zstd_bytes = 255444794

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220512"
previous_tag = "2022-05-12"
previous_file = "alpine-mate_i386_2022-05-12_00-31-rootfs.tar.zst"
previous_sha256 = "b2a543e624724bfe79aba6e50cc9d78ee7cb7f0706fd0f02f8e7c35103885640"

current_version = "latest02"
current_date = "20220519"
old_file = "alpine-mate_i386_2022-05-05_01-03-rootfs.tar.zst"
old_sha256 = "012f13622adaf9ed9a0a686c86762c4d5c17ebd8ba558adaf7602af5c935c589"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-mate_i386_2022-05-19_00-28-rootfs.tar.zst
# SHA256SUM=babfb001eed3db0977e770b7a020c5419f16f7633cc6148d3fc3ad2df32f0ff1
# BUILD_DATE=20220519
# BUILD_TAG=2022-05-19
# STATUS=completed
# VERSION=latest02
# END_TIME=00:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-19
begin = 2022-05-19 00:06:31.541899655+00:00
start-sync_0 = 00:24:37
start-zstd = 00:25:22
start-sync_1 = 00:27:40
end-sync_1 = 00:28:02
end = 2022-05-19 00:28:02.515218026+00:00

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
