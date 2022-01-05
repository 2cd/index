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

## debian-lxde-armv7.toml

```toml
[main]
name = "debian"
tag = ["lxde", "2022-01-05"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "debian-lxde_armhf_2022-01-05_13-00.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "9d8f1cc4f8ce22e091ef0029d1577523f894a3583304cf8086685ca232e12e20"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.4G"
tar_bytes = 2556647936

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "812M"
zstd_bytes = 851167590

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211229"
previous_tag = "2021-12-29"
previous_file = "debian-lxde_armhf_2021-12-29_13-06-rootfs.tar.zst"
previous_sha256 = "7cb16ca85d75d4347cac8c7c707914edefad1cbf76cc32a59b9d16e8e86652b6"

current_version = "latest02"
current_date = "20220105"
old_file = "debian-lxde_armhf_2021-12-22_13-01-rootfs.tar.zst"
old_sha256 = "6008556433f14ac2028f24eb26dcad3b6fcd8285fa5da8c6790664f6629f95f1"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2022-01-05_13-00-rootfs.tar.zst
# SHA256SUM=9d8f1cc4f8ce22e091ef0029d1577523f894a3583304cf8086685ca232e12e20
# BUILD_DATE=20220105
# BUILD_TAG=2022-01-05
# STATUS=completed
# VERSION=latest02
# END_TIME=13:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-05
begin = 2022-01-05 12:22:32.135149928+00:00
start-sync_0 = 12:51:24
start-zstd = 12:53:18
start-sync_1 = 12:59:14
end-sync_1 = 13:00:06
end = 2022-01-05 13:00:06.444076466+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-1) 2.33'
zsh = 'zsh 5.8 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
