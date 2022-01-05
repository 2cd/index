# debian-mate-amd64

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
    --name debian-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-mate-amd64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```sh
    startvnc
```

or

```sh
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

## debian-mate-amd64.toml

```toml
[main]
name = "debian"
tag = ["mate", "2022-01-05"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "debian-mate_amd64_2022-01-05_12-41.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "8740942f52ac81ba6fd6391a97f838e07f5b0e6ea2005fb864381c87248758d3"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.5G"
tar_bytes = 3655838208

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "958M"
zstd_bytes = 1003751378

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220105"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-mate_amd64_2022-01-05_12-41-rootfs.tar.zst
# SHA256SUM=8740942f52ac81ba6fd6391a97f838e07f5b0e6ea2005fb864381c87248758d3
# BUILD_DATE=20220105
# BUILD_TAG=2022-01-05
# STATUS=completed
# VERSION=latest01
# END_TIME=12:41

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-05
begin = 2022-01-05 12:22:33.964321880+00:00
start-sync_0 = 12:28:06
start-zstd = 12:31:17
start-sync_1 = 12:40:51
end-sync_1 = 12:41:54
end = 2022-01-05 12:41:54.173361062+00:00

[server]
repo = "cake233/debian-mate-amd64"

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (Debian GLIBC 2.33-1) 2.33'
zsh = 'zsh 5.8 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
