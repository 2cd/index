# ubuntu-kde-armv7

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
    --name ubuntu-kde-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-armv7 zsh
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

## ubuntu-kde-armv7.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2022-04-04", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "ubuntu-kde_armhf_2022-04-05_00-04.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "81304c4d35f0fcf17ebf54747dcd7a0dc5c947eb3886411c926d8c290e439495"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.9G"
tar_bytes = 3049628672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "948M"
zstd_bytes = 993772975

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220329"
previous_tag = "2022-03-28"
previous_file = "ubuntu-kde_armhf_2022-03-29_00-03-rootfs.tar.zst"
previous_sha256 = "db57428fedcca75cc15de168b3b0b4508fa5ee1148f5d94063f3ba1acb95cf87"

current_version = "latest01"
current_date = "20220405"
old_file = "ubuntu-kde_armhf_2022-03-22_01-04-rootfs.tar.zst"
old_sha256 = "cddd1425f415881979185f7e76abcf912f9c4401ba2a3469246697f4a311ef53"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-kde_armhf_2022-04-05_00-04-rootfs.tar.zst
# SHA256SUM=81304c4d35f0fcf17ebf54747dcd7a0dc5c947eb3886411c926d8c290e439495
# BUILD_DATE=20220405
# BUILD_TAG=2022-04-04
# STATUS=completed
# VERSION=latest01
# END_TIME=00:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-04
begin = 2022-04-04 23:21:34.999663951+00:00
start-sync_0 = 23:52:17
start-zstd = 23:54:29
start-sync_1 = 00:03:26
end-sync_1 = 00:04:28
end = 2022-04-05 00:04:28.342472693+00:00

[server]
repo = "cake233/ubuntu-kde-armv7"

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.8.1 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
