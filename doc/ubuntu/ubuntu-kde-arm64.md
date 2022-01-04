# ubuntu-kde-arm64

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
    --name ubuntu-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-arm64 zsh
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

## ubuntu-kde-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2022-01-04", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "ubuntu-kde_arm64_2022-01-04_01-26.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "3d1288eaf6003904a7f52a445b7817afd8fd72cc3c22a8965b81d694ff3ac490"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.2G"
tar_bytes = 4424007168

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1234795720

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211228"
previous_tag = "2021-12-28"
previous_file = "ubuntu-kde_arm64_2021-12-28_01-14-rootfs.tar.zst"
previous_sha256 = "ad63dcaebed3200d778a9148e6c769d5e3ca40ae7bff8cf7517418791cc2ad34"

current_version = "latest02"
current_date = "20220104"
old_file = "ubuntu-kde_arm64_2021-12-21_01-19-rootfs.tar.zst"
old_sha256 = "a1c362353b79c036397f5d848594b9cfa16e46b8e8447deb9d32ca312f1a5c53"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-kde_arm64_2022-01-04_01-26-rootfs.tar.zst
# SHA256SUM=3d1288eaf6003904a7f52a445b7817afd8fd72cc3c22a8965b81d694ff3ac490
# BUILD_DATE=20220104
# BUILD_TAG=2022-01-04
# STATUS=completed
# VERSION=latest02
# END_TIME=01:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-04
begin = 2022-01-04 00:22:45.951832049+00:00
start-sync_0 = 01:06:37
start-zstd = 01:11:00
start-sync_1 = 01:24:38
end-sync_1 = 01:26:04
end = 2022-01-04 01:26:04.217274328+00:00

[server]
repo = "cake233/ubuntu-kde-arm64"

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
