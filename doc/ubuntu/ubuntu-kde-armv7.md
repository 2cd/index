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
tag = ["kde", "2023-10-17", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_armhf_2023-10-17_01-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6ced158f5f7005fb873573ddfebdfac5b6ba475b8fc650fb098ea007ae59fdaa"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.9G"
tar_bytes = 4095849984

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1311865661

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231010"
previous_tag = "2023-10-10"
previous_file = "ubuntu-kde_armhf_2023-10-10_01-36-rootfs.tar.zst"
previous_sha256 = "09c1fc61890643c9c3074e3caab8bab5fb4ba2d55e93ecbb8c5da10342139f22"

current_version = "latest02"
current_date = "20231017"
old_file = "ubuntu-kde_armhf_2023-10-03_01-20-rootfs.tar.zst"
old_sha256 = "f24cd5d564f68d0442ae6ac8b991a9b19a3b355195e2d61967d024faf040fa3f"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-kde_armhf_2023-10-17_01-26-rootfs.tar.zst
# SHA256SUM=6ced158f5f7005fb873573ddfebdfac5b6ba475b8fc650fb098ea007ae59fdaa
# BUILD_DATE=20231017
# BUILD_TAG=2023-10-17
# STATUS=completed
# VERSION=latest02
# END_TIME=01:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-17
begin = 2023-10-17 00:33:55.802472111+00:00
start-sync_0 = 01:08:01
start-zstd = 01:10:57
start-sync_1 = 01:25:21
end-sync_1 = 01:26:53
end = 2023-10-17 01:26:53.143536000+00:00

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
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
