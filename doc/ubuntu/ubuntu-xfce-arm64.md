# ubuntu-xfce-arm64

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
    --name ubuntu-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-xfce-arm64 zsh
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

## ubuntu-xfce-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2023-10-17", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_arm64_2023-10-17_02-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a49b1aa89c35946b8b8188c07376fbca25fb0284e26719bbb6cb8ad3429c4d8d"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4861342720

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1284559741

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231010"
previous_tag = "2023-10-10"
previous_file = "ubuntu-xfce_arm64_2023-10-10_01-48-rootfs.tar.zst"
previous_sha256 = "cde8b82b7dfe0f150450f92730e1fe1ea69625494a2488f75ef1521be577da74"

current_version = "latest02"
current_date = "20231017"
old_file = "ubuntu-xfce_arm64_2023-10-03_01-36-rootfs.tar.zst"
old_sha256 = "6483671dfff5c41ebd722278652595dbc75a0e4412c8618ec3a6e86d5d18b186"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-xfce_arm64_2023-10-17_02-10-rootfs.tar.zst
# SHA256SUM=a49b1aa89c35946b8b8188c07376fbca25fb0284e26719bbb6cb8ad3429c4d8d
# BUILD_DATE=20231017
# BUILD_TAG=2023-10-17
# STATUS=completed
# VERSION=latest02
# END_TIME=02:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-17
begin = 2023-10-17 00:33:59.925286393+00:00
start-sync_0 = 01:43:47
start-zstd = 01:48:19
start-sync_1 = 02:09:10
end-sync_1 = 02:10:56
end = 2023-10-17 02:10:57.003938365+00:00

[server]
repo = "cake233/ubuntu-xfce-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu6) 2.38'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
