# debian-kde-arm64

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
    --name debian-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-kde-arm64 zsh
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

## debian-kde-arm64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2023-08-16"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_arm64_2023-08-16_13-50.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3198e1a8ff77c72952463f39f592fd9f9725a89f8b7c96774a4114ed5b4aa4dc"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.1G"
tar_bytes = 6513717760

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1824907562

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230809"
previous_tag = "2023-08-09"
previous_file = "debian-kde_arm64_2023-08-09_13-43-rootfs.tar.zst"
previous_sha256 = "c5233f230870a1c36476462641c1a3d9f3e65a3dc84c7dbd5bae11fbc226d54a"

current_version = "latest02"
current_date = "20230816"
old_file = "debian-kde_arm64_2023-08-02_13-44-rootfs.tar.zst"
old_sha256 = "ea347eeb610188d1b6af5d3cb40ab559ea65cbd0a85b5af87061cdd3c8099df8"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2023-08-16_13-50-rootfs.tar.zst
# SHA256SUM=3198e1a8ff77c72952463f39f592fd9f9725a89f8b7c96774a4114ed5b4aa4dc
# BUILD_DATE=20230816
# BUILD_TAG=2023-08-16
# STATUS=completed
# VERSION=latest02
# END_TIME=13:50

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-16
begin = 2023-08-16 12:24:29.844319726+00:00
start-sync_0 = 13:13:03
start-zstd = 13:20:13
start-sync_1 = 13:47:47
end-sync_1 = 13:50:06
end = 2023-08-16 13:50:06.742093040+00:00

[server]
repo = "cake233/debian-kde-arm64"

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
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
