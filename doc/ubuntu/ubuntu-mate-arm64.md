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
tag = ["mate", "2022-09-06", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-mate_arm64_2022-09-06_01-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "cba1ca9684816973c3336bbf6e210456b754485bdf7e3586bb7360be68f685b0"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.2G"
tar_bytes = 4448449536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1198165256

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220830"
previous_tag = "2022-08-30"
previous_file = "ubuntu-mate_arm64_2022-08-30_00-56-rootfs.tar.zst"
previous_sha256 = "098e9800f0ad6fdca0160b927748348689a901f21789ee022206831459f05222"

current_version = "latest02"
current_date = "20220906"
old_file = "ubuntu-mate_arm64_2022-08-23_01-13-rootfs.tar.zst"
old_sha256 = "c19e89f6be4ad59ce8ab19f2dcb5fcdbf5096f1c6686b33eeb11970e1e110578"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-mate_arm64_2022-09-06_01-08-rootfs.tar.zst
# SHA256SUM=cba1ca9684816973c3336bbf6e210456b754485bdf7e3586bb7360be68f685b0
# BUILD_DATE=20220906
# BUILD_TAG=2022-09-06
# STATUS=completed
# VERSION=latest02
# END_TIME=01:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-06
begin = 2022-09-06 00:22:01.733703192+00:00
start-sync_0 = 00:49:54
start-zstd = 00:53:23
start-sync_1 = 01:07:24
end-sync_1 = 01:08:33
end = 2022-09-06 01:08:33.668726678+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu2) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
