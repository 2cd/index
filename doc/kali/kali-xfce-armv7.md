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
tag = ["xfce", "2022-12-08"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_armhf_2022-12-08_13-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1bff3547142c58db7e32cc892d28b1b6efdd9d55bed6d5c9ea96886c12f6b00c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3815635968

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1213070913

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221201"
previous_tag = "2022-12-01"
previous_file = "kali-xfce_armhf_2022-12-01_13-08-rootfs.tar.zst"
previous_sha256 = "6861a97049d48ece0bc6602ba92651521d8ae59c112252db524f4442c10814cc"

current_version = "latest02"
current_date = "20221208"
old_file = "kali-xfce_armhf_2022-11-24_13-14-rootfs.tar.zst"
old_sha256 = "8f14197018267da37ed09848ca6e44be2ab4c41ee3e65f215dbf9703f163c1f0"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-xfce_armhf_2022-12-08_13-06-rootfs.tar.zst
# SHA256SUM=1bff3547142c58db7e32cc892d28b1b6efdd9d55bed6d5c9ea96886c12f6b00c
# BUILD_DATE=20221208
# BUILD_TAG=2022-12-08
# STATUS=completed
# VERSION=latest02
# END_TIME=13:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-08
begin = 2022-12-08 12:19:52.166640726+00:00
start-sync_0 = 12:51:55
start-zstd = 12:54:45
start-sync_1 = 13:04:42
end-sync_1 = 13:06:40
end = 2022-12-08 13:06:40.825318964+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-4) 2.36'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
