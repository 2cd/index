# kali-xfce-amd64

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
    --name kali-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-amd64 zsh
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

## kali-xfce-amd64.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2022-11-10"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_amd64_2022-11-10_12-58.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4640d2d59e7a6df98af62c605cd40e47722c1425a7b2c11c160dd76e3a81d61c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.9G"
tar_bytes = 4171251712

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1203327092

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221103"
previous_tag = "2022-11-03"
previous_file = "kali-xfce_amd64_2022-11-03_12-44-rootfs.tar.zst"
previous_sha256 = "95e13eac390b915f1a48bb045393196ad21cd2a72a7a1b8eeb805523fb073f0b"

current_version = "latest01"
current_date = "20221110"
old_file = "kali-xfce_amd64_2022-10-27_12-47-rootfs.tar.zst"
old_sha256 = "3f37054d013f21651633f9868630401f6e20504518d306190adcc994edabedc2"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-xfce_amd64_2022-11-10_12-58-rootfs.tar.zst
# SHA256SUM=4640d2d59e7a6df98af62c605cd40e47722c1425a7b2c11c160dd76e3a81d61c
# BUILD_DATE=20221110
# BUILD_TAG=2022-11-10
# STATUS=completed
# VERSION=latest01
# END_TIME=12:58

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-10
begin = 2022-11-10 12:23:54.532632782+00:00
start-sync_0 = 12:33:47
start-zstd = 12:38:32
start-sync_1 = 12:57:31
end-sync_1 = 12:58:57
end = 2022-11-10 12:58:57.731354423+00:00

[server]
repo = "cake233/kali-xfce-amd64"

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (Debian GLIBC 2.35-4) 2.35'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
