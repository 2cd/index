# ubuntu-mate-arm64

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
    --name ubuntu-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-mate-arm64 zsh
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

## ubuntu-mate-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["mate", "2023-12-19", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-mate_arm64_2023-12-19_02-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e6e1f19ee136e59df7fcf67f064b7c33af76181a2633e1d5008758d7e239e715"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4401155072

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1142532071

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231128"
previous_tag = "2023-11-28"
previous_file = "ubuntu-mate_arm64_2023-11-28_01-16-rootfs.tar.zst"
previous_sha256 = "826ce581c0964e69cd83f610aeb6349c3665a2b3147e5dc41d42bea18d68a593"

current_version = "latest02"
current_date = "20231219"
old_file = "ubuntu-mate_arm64_2023-11-21_01-14-rootfs.tar.zst"
old_sha256 = "b5c60ec127ea76ca9a2c9593fdb3d5f4270ddfc467ed6735c56690c16b72d494"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-mate_arm64_2023-12-19_02-04-rootfs.tar.zst
# SHA256SUM=e6e1f19ee136e59df7fcf67f064b7c33af76181a2633e1d5008758d7e239e715
# BUILD_DATE=20231219
# BUILD_TAG=2023-12-19
# STATUS=completed
# VERSION=latest02
# END_TIME=02:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-19
begin = 2023-12-19 00:36:06.326468942+00:00
start-sync_0 = 01:50:52
start-zstd = 01:53:04
start-sync_1 = 02:03:28
end-sync_1 = 02:04:18
end = 2023-12-19 02:04:18.262077825+00:00

[server]
repo = "cake233/ubuntu-mate-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-3ubuntu1) 2.38'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
