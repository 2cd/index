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
tag = ["xfce", "2023-06-15"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_armhf_2023-06-15_13-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "77ecf395d85ebfddfbe8b44cde26fa4c6d1d78278d8698480e478b8fa62456c8"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.7G"
tar_bytes = 2825352704

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "814M"
zstd_bytes = 853281905

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230608"
previous_tag = "2023-06-08"
previous_file = "kali-xfce_armhf_2023-06-08_13-33-rootfs.tar.zst"
previous_sha256 = "e61693f89c590bb9f961b8d0ccc314523009a24defe793620ae768e7c75ede03"

current_version = "latest01"
current_date = "20230615"
old_file = "kali-xfce_armhf_2023-06-01_13-46-rootfs.tar.zst"
old_sha256 = "59619f3b089bd09582947d020feed9fe04ce56610412e773f39221ead7af1f5c"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-xfce_armhf_2023-06-15_13-26-rootfs.tar.zst
# SHA256SUM=77ecf395d85ebfddfbe8b44cde26fa4c6d1d78278d8698480e478b8fa62456c8
# BUILD_DATE=20230615
# BUILD_TAG=2023-06-15
# STATUS=completed
# VERSION=latest01
# END_TIME=13:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-15
begin = 2023-06-15 12:25:02.303666307+00:00
start-sync_0 = 13:15:09
start-zstd = 13:17:10
start-sync_1 = 13:26:05
end-sync_1 = 13:26:59
end = 2023-06-15 13:26:59.352583536+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabi)'

[port]
tcp = [5902, 36080]
```
