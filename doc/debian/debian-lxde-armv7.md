# debian-lxde-armv7

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
    --name debian-lxde-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-lxde-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-lxde-armv7 zsh
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

## debian-lxde-armv7.toml

```toml
[main]
name = "debian"
tag = ["lxde", "2023-11-08"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_armhf_2023-11-08_12-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "10d3c3ce13c2d7b1ce3f189088f903c28487119dd195c21e082ff296defcd8b7"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3171346432

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "955M"
zstd_bytes = 1000428061

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231025"
previous_tag = "2023-10-25"
previous_file = "debian-lxde_armhf_2023-10-25_13-32-rootfs.tar.zst"
previous_sha256 = "16d4c4df24138a3c795fbb05f94058d118c4759102a9951501ded0a021cddb46"

current_version = "latest02"
current_date = "20231108"
old_file = "debian-lxde_armhf_2023-10-18_13-33-rootfs.tar.zst"
old_sha256 = "0a543f8451bab9cfc33a6a1fb8fb9a5c5bfd3a0b28070d23cb1446ba799bd12f"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2023-11-08_12-59-rootfs.tar.zst
# SHA256SUM=10d3c3ce13c2d7b1ce3f189088f903c28487119dd195c21e082ff296defcd8b7
# BUILD_DATE=20231108
# BUILD_TAG=2023-11-08
# STATUS=completed
# VERSION=latest02
# END_TIME=12:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-08
begin = 2023-11-08 12:31:26.314166635+00:00
start-sync_0 = 12:49:36
start-zstd = 12:51:09
start-sync_1 = 12:58:26
end-sync_1 = 12:59:29
end = 2023-11-08 12:59:29.887650600+00:00

[server]
repo = "cake233/debian-lxde-armv7"

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
