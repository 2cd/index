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
tag = ["xfce", "2024-01-18"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_armhf_2024-01-18_13-22.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9c57c12360d842defcc3156b37d5d1843aa2fa7df9674c2ea78f7a0e488f5e06"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.7G"
tar_bytes = 2872044544

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "818M"
zstd_bytes = 857040958

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231123"
previous_tag = "2023-11-23"
previous_file = "kali-xfce_armhf_2023-11-23_13-26-rootfs.tar.zst"
previous_sha256 = "d2646d1827516fffab846d879e2614458afcbfec7e55130902408d1510fd8ac7"

current_version = "latest02"
current_date = "20240118"
old_file = "kali-xfce_armhf_2023-11-16_13-20-rootfs.tar.zst"
old_sha256 = "8cb461452ac401cc89cf64e201b1e2a38ed624df3eb6ad90f3a80011059be440"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-xfce_armhf_2024-01-18_13-22-rootfs.tar.zst
# SHA256SUM=9c57c12360d842defcc3156b37d5d1843aa2fa7df9674c2ea78f7a0e488f5e06
# BUILD_DATE=20240118
# BUILD_TAG=2024-01-18
# STATUS=completed
# VERSION=latest02
# END_TIME=13:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-18
begin = 2024-01-18 12:36:32.466726215+00:00
start-sync_0 = 13:12:37
start-zstd = 13:14:11
start-sync_1 = 13:21:45
end-sync_1 = 13:22:31
end = 2024-01-18 13:22:31.900435950+00:00

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
