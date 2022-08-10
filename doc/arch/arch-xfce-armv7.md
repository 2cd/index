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

## arch-xfce-armv7.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2022-08-10"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_armhf_2022-08-10_01-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "729e668d9507ce57b7c2aa6611beada6b638c79d4db6d21b204f079ab77c4984"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.2G"
tar_bytes = 3360007168

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1095668472

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220713"
previous_tag = "2022-07-13"
previous_file = "arch-xfce_armhf_2022-07-13_01-14-rootfs.tar.zst"
previous_sha256 = "7d24b642e9c78e81b6c6870c1daa39e180a095b6264f0ef8ec147bc02a973a5c"

current_version = "latest01"
current_date = "20220810"
old_file = "arch-xfce_armhf_2022-07-06_00-57-rootfs.tar.zst"
old_sha256 = "90ee3c58f78d601862e24861304b25860b3007179ac2628b3d23b356c8a03401"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-xfce_armhf_2022-08-10_01-04-rootfs.tar.zst
# SHA256SUM=729e668d9507ce57b7c2aa6611beada6b638c79d4db6d21b204f079ab77c4984
# BUILD_DATE=20220810
# BUILD_TAG=2022-08-10
# STATUS=completed
# VERSION=latest01
# END_TIME=01:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-10
begin = 2022-08-10 00:32:19.353764209+00:00
start-sync_0 = 00:49:42
start-zstd = 00:52:18
start-sync_1 = 01:03:37
end-sync_1 = 01:04:43
end = 2022-08-10 01:04:43.700485995+00:00

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (armv7l-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
