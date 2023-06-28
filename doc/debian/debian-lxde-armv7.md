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
tag = ["lxde", "2023-06-28"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_armhf_2023-06-28_13-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "336ded3b0d00711aead024c48ab612e4432afe08f5fbd27b53ef2ef3e3c4aa17"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3134563840

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "949M"
zstd_bytes = 994309866

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230621"
previous_tag = "2023-06-21"
previous_file = "debian-lxde_armhf_2023-06-21_13-00-rootfs.tar.zst"
previous_sha256 = "02613a8374429152328818ea2559c699d5cafbebaf6fa9ce301b0e9f55d22740"

current_version = "latest01"
current_date = "20230628"
old_file = "debian-lxde_armhf_2023-06-14_12-58-rootfs.tar.zst"
old_sha256 = "aa03cac63900e2833a8246dc4ed16081706be832afb582fab1135ac4c3f2e70e"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2023-06-28_13-06-rootfs.tar.zst
# SHA256SUM=336ded3b0d00711aead024c48ab612e4432afe08f5fbd27b53ef2ef3e3c4aa17
# BUILD_DATE=20230628
# BUILD_TAG=2023-06-28
# STATUS=completed
# VERSION=latest01
# END_TIME=13:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-28
begin = 2023-06-28 12:20:58.478302299+00:00
start-sync_0 = 12:50:20
start-zstd = 12:52:55
start-sync_1 = 13:05:02
end-sync_1 = 13:06:14
end = 2023-06-28 13:06:14.227159828+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
