# fedora-xfce-arm64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
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
    --name fedora-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-xfce-arm64 zsh
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

## fedora-xfce-arm64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2022-12-13"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_arm64_2022-12-13_14-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "965f4fffbc9a7e0468000b17e63e7651deff1b5b0a46fd8e8f8b0726afbab546"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.6G"
tar_bytes = 6006429696

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1603686492

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221206"
previous_tag = "2022-12-06"
previous_file = "fedora-xfce_arm64_2022-12-06_14-15-rootfs.tar.zst"
previous_sha256 = "072c05e06fed16a93fb75ea9b426fecf4a957bc8baac512a764e06f62afc4201"

current_version = "latest01"
current_date = "20221213"
old_file = "fedora-xfce_arm64_2022-11-29_14-11-rootfs.tar.zst"
old_sha256 = "574c627c1a6204d7777ff47636bdf3c7aa73d89f5d44f2e01905039d5aa0e6d3"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-xfce_arm64_2022-12-13_14-11-rootfs.tar.zst
# SHA256SUM=965f4fffbc9a7e0468000b17e63e7651deff1b5b0a46fd8e8f8b0726afbab546
# BUILD_DATE=20221213
# BUILD_TAG=2022-12-13
# STATUS=completed
# VERSION=latest01
# END_TIME=14:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-13
begin = 2022-12-13 12:41:33.017035112+00:00
start-sync_0 = 13:47:15
start-zstd = 13:51:49
start-sync_1 = 14:09:22
end-sync_1 = 14:11:58
end = 2022-12-13 14:11:58.754434935+00:00

[server]
repo = "cake233/fedora-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
