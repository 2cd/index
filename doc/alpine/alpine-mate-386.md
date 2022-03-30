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
tag = ["mate", "2022-03-30"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
x11_or_wayland = true

[file]
name = "alpine-mate_i386_2022-03-30_23-27.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "b1131e4e24f57cae72e58248571685688d4901ce084cb76a312446ca3f3df4a7"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "796M"
tar_bytes = 834051072

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "250M"
zstd_bytes = 262051313

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220324"
previous_tag = "2022-03-24"
previous_file = "alpine-mate_i386_2022-03-24_00-30-rootfs.tar.zst"
previous_sha256 = "bb0746eed1c824b6d001967494729fead535113d7d59ad405ed4f854a88c4b31"

current_version = "latest02"
current_date = "20220330"
old_file = "alpine-mate_i386_2022-03-17_00-34-rootfs.tar.zst"
old_sha256 = "87dbbf2db3ee45f9c85a73095d7e70a94406da222ef81d2e2b67e99b813d2658"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-mate_i386_2022-03-30_23-27-rootfs.tar.zst
# SHA256SUM=b1131e4e24f57cae72e58248571685688d4901ce084cb76a312446ca3f3df4a7
# BUILD_DATE=20220330
# BUILD_TAG=2022-03-30
# STATUS=completed
# VERSION=latest02
# END_TIME=23:27

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-30
begin = 2022-03-30 23:06:34.466551292+00:00
start-sync_0 = 23:23:24
start-zstd = 23:24:06
start-sync_1 = 23:26:46
end-sync_1 = 23:27:06
end = 2022-03-30 23:27:06.534132924+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'musl libc (i386) Version 1.2.2'
zsh = 'zsh 5.8.1 (i586-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
