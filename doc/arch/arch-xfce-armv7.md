# arch-xfce-armv7

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not armv7, then install qemu & binfmt-support.
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
    --name arch-xfce-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-armv7 zsh
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

## arch-xfce-armv7.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2022-01-12"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "arch-xfce_armhf_2022-01-12_01-27.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "31002fbf4dd10a3717aa1a5774aa8141182bcc1169e4ae14a107ea10be239956"

# zstd: [1-22]
zstd-level = 15

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.1G"
tar_bytes = 3251240448

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1188358138

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211215"
previous_tag = "2021-12-15"
previous_file = "arch-xfce_armhf_2021-12-15_01-24-rootfs.tar.zst"
previous_sha256 = "2d8440c273d812eedc27e3e43db965923cb1a91198e41b4d63a5a9c39a3a88d3"

current_version = "latest01"
current_date = "20220112"
old_file = "arch-xfce_armhf_2021-12-12_07-21-rootfs.tar.zst"
old_sha256 = "4af0b7682067d48f5cfd5aa0babc7ef515be0d211dfd1fbd2f74fde946e8555b"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-xfce_armhf_2022-01-12_01-27-rootfs.tar.zst
# SHA256SUM=31002fbf4dd10a3717aa1a5774aa8141182bcc1169e4ae14a107ea10be239956
# BUILD_DATE=20220112
# BUILD_TAG=2022-01-12
# STATUS=completed
# VERSION=latest01
# END_TIME=01:27

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-12
begin = 2022-01-12 00:24:46.477286388+00:00
start-sync_0 = 01:19:47
start-zstd = 01:22:35
start-sync_1 = 01:26:32
end-sync_1 = 01:27:43
end = 2022-01-12 01:27:43.274070112+00:00

[server]
repo = "cake233/arch-xfce-armv7"

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
ldd = 'ldd (GNU libc) 2.32'
zsh = 'zsh 5.8 (armv7l-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
