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
tag = ["xfce", "2023-06-13", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_arm64_2023-06-13_01-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "be96f6a45c839a595719566c298f83a3d17867f97c4d87a1649dcfc613b3c33a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3907614208

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1023M"
zstd_bytes = 1071989085

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230606"
previous_tag = "2023-06-06"
previous_file = "ubuntu-xfce_arm64_2023-06-06_00-53-rootfs.tar.zst"
previous_sha256 = "92fc45e87c4b8247f52d9ae1a83a0ee59dc79cc2fc9093aacee83732e6328a0a"

current_version = "latest01"
current_date = "20230613"
old_file = "ubuntu-xfce_arm64_2023-05-30_00-52-rootfs.tar.zst"
old_sha256 = "1653bded355c610d2ac2f14cb40c6b1dfe0b3d3dd278d3bf796acc06149731e3"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-xfce_arm64_2023-06-13_01-01-rootfs.tar.zst
# SHA256SUM=be96f6a45c839a595719566c298f83a3d17867f97c4d87a1649dcfc613b3c33a
# BUILD_DATE=20230613
# BUILD_TAG=2023-06-13
# STATUS=completed
# VERSION=latest01
# END_TIME=01:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-13
begin = 2023-06-13 00:03:13.629047662+00:00
start-sync_0 = 00:41:12
start-zstd = 00:44:47
start-sync_1 = 01:00:22
end-sync_1 = 01:01:35
end = 2023-06-13 01:01:35.722416825+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
