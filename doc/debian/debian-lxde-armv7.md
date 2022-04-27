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
tag = ["lxde", "2022-04-27"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_armhf_2022-04-27_13-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "28d900408414d1eeb22e365b23e302de7d679d6afb23ad74b05a28505c06d098"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.8G"
tar_bytes = 2944393728

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "912M"
zstd_bytes = 956111435

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220420"
previous_tag = "2022-04-20"
previous_file = "debian-lxde_armhf_2022-04-20_12-56-rootfs.tar.zst"
previous_sha256 = "0f2c90a53019fb4768ca0eb84d851d5921644f30291c06b203603c4b4eb99193"

current_version = "latest02"
current_date = "20220427"
old_file = "debian-lxde_armhf_2022-04-13_12-55-rootfs.tar.zst"
old_sha256 = "c62031cd4e940658a3da4fa3b417c483f7d5f43fa16205bb12a5bb994797faad"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2022-04-27_13-03-rootfs.tar.zst
# SHA256SUM=28d900408414d1eeb22e365b23e302de7d679d6afb23ad74b05a28505c06d098
# BUILD_DATE=20220427
# BUILD_TAG=2022-04-27
# STATUS=completed
# VERSION=latest02
# END_TIME=13:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-27
begin = 2022-04-27 12:22:47.271596212+00:00
start-sync_0 = 12:51:03
start-zstd = 12:53:28
start-sync_1 = 13:02:48
end-sync_1 = 13:03:58
end = 2022-04-27 13:03:58.349955157+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.8.1 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
