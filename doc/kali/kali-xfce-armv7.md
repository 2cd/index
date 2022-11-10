# kali-xfce-armv7

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
    --name kali-xfce-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-armv7 zsh
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

## kali-xfce-armv7.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2022-11-10"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_armhf_2022-11-10_13-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "43384e64868cb70deadce906659b7586b65da7d67b16a0b3ec78f7fd1da9650f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.5G"
tar_bytes = 3728087040

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1191974886

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221103"
previous_tag = "2022-11-03"
previous_file = "kali-xfce_armhf_2022-11-03_13-03-rootfs.tar.zst"
previous_sha256 = "319ff9d8de3fae4854c7aa1e7aec3c18596906f7c9e1934d0b88e33bfb0dc486"

current_version = "latest02"
current_date = "20221110"
old_file = "kali-xfce_armhf_2022-10-27_13-15-rootfs.tar.zst"
old_sha256 = "2609cd985dcc0335421a0b44cdddee453634bbf45defcf51e1a71288ce36f4a5"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-xfce_armhf_2022-11-10_13-14-rootfs.tar.zst
# SHA256SUM=43384e64868cb70deadce906659b7586b65da7d67b16a0b3ec78f7fd1da9650f
# BUILD_DATE=20221110
# BUILD_TAG=2022-11-10
# STATUS=completed
# VERSION=latest02
# END_TIME=13:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-10
begin = 2022-11-10 12:23:53.952939845+00:00
start-sync_0 = 12:56:51
start-zstd = 12:59:34
start-sync_1 = 13:13:11
end-sync_1 = 13:14:24
end = 2022-11-10 13:14:24.646385331+00:00

[server]
repo = "cake233/kali-xfce-armv7"

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
ldd = 'ldd (Debian GLIBC 2.35-4) 2.35'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
