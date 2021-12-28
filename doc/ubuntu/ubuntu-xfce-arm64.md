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

```sh
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
tag = ["xfce", "2021-12-28", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "ubuntu-xfce_arm64_2021-12-28_01-06.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "e917b4074ff253b77fe2d1dc90f65dfad8b7a8ebb255e13a372d1f432aa44c16"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.4G"
tar_bytes = 3573797376

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "894M"
zstd_bytes = 937171758

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211221"
previous_tag = "2021-12-21"
previous_file = "ubuntu-xfce_arm64_2021-12-21_01-04-rootfs.tar.zst"
previous_sha256 = "62c4704ddd66b27e02cba27c306b9588897003d5d08f65e2cb5c27621fea16b2"

current_version = "latest01"
current_date = "20211228"
old_file = "ubuntu-xfce_arm64_2021-12-14_01-38-rootfs.tar.zst"
old_sha256 = "8e56e4c699e29a8995981a798aced532831ddd79e259cd3c19d444d6ca83069c"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-xfce_arm64_2021-12-28_01-06-rootfs.tar.zst
# SHA256SUM=e917b4074ff253b77fe2d1dc90f65dfad8b7a8ebb255e13a372d1f432aa44c16
# BUILD_DATE=20211228
# BUILD_TAG=2021-12-28
# STATUS=completed
# VERSION=latest01
# END_TIME=01:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-28
begin = 2021-12-28 00:22:11.759611709+00:00
start-sync_0 = 00:53:33
start-zstd = 00:56:14
start-sync_1 = 01:05:00
end-sync_1 = 01:06:00
end = 2021-12-28 01:06:00.324398194+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.34-0ubuntu3) 2.34'
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
