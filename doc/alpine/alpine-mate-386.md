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
tag = ["mate", "2023-02-23"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_i386_2023-02-23_00-21.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "50e3f1e1eca986c4645482440f6ffc1a4cc08664ce8b7070f9e0d949eb3bb59e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "761M"
tar_bytes = 797769216

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "239M"
zstd_bytes = 250290730

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230216"
previous_tag = "2023-02-16"
previous_file = "alpine-mate_i386_2023-02-16_00-18-rootfs.tar.zst"
previous_sha256 = "5f080d9d59a768f86907780d4c12692f63a351ee36ce125bfd0c6fbeaf0efa5d"

current_version = "latest01"
current_date = "20230223"
old_file = "alpine-mate_i386_2023-02-09_00-14-rootfs.tar.zst"
old_sha256 = "5b61c57716b49725bcc85b8ba18f1948541c2908751be2d1f24dbe5efc31afcb"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-mate_i386_2023-02-23_00-21-rootfs.tar.zst
# SHA256SUM=50e3f1e1eca986c4645482440f6ffc1a4cc08664ce8b7070f9e0d949eb3bb59e
# BUILD_DATE=20230223
# BUILD_TAG=2023-02-23
# STATUS=completed
# VERSION=latest01
# END_TIME=00:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-23
begin = 2023-02-23 00:07:14.359266015+00:00
start-sync_0 = 00:17:09
start-zstd = 00:17:56
start-sync_1 = 00:20:49
end-sync_1 = 00:21:13
end = 2023-02-23 00:21:13.528805827+00:00

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
zsh = 'zsh 5.9 (i586-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
