# kali-xfce-armv7

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
    --name kali-xfce-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-armv7 zsh
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

## kali-xfce-armv7.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2023-11-16"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_armhf_2023-11-16_13-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8cb461452ac401cc89cf64e201b1e2a38ed624df3eb6ad90f3a80011059be440"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.7G"
tar_bytes = 2852373504

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "812M"
zstd_bytes = 850877476

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231109"
previous_tag = "2023-11-09"
previous_file = "kali-xfce_armhf_2023-11-09_13-20-rootfs.tar.zst"
previous_sha256 = "db8db6d1e61a2c8fa914af55da6ea94d3631e45aa853412d29d7ba1b5f05850d"

current_version = "latest02"
current_date = "20231116"
old_file = "kali-xfce_armhf_2023-10-26_14-08-rootfs.tar.zst"
old_sha256 = "5d4c136d328b7ce2a0b1edc9269d628612d18eb64a8cc275e6f40b43733ae7f8"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-xfce_armhf_2023-11-16_13-20-rootfs.tar.zst
# SHA256SUM=8cb461452ac401cc89cf64e201b1e2a38ed624df3eb6ad90f3a80011059be440
# BUILD_DATE=20231116
# BUILD_TAG=2023-11-16
# STATUS=completed
# VERSION=latest02
# END_TIME=13:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-16
begin = 2023-11-16 12:32:38.392989290+00:00
start-sync_0 = 13:11:05
start-zstd = 13:12:36
start-sync_1 = 13:19:45
end-sync_1 = 13:20:22
end = 2023-11-16 13:20:22.870016052+00:00

[server]
repo = "cake233/kali-xfce-armv7"

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabi)'

[port]
tcp = [5902, 36080]
```
