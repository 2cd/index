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
tag = ["xfce", "2023-07-06"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_armhf_2023-07-06_14-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "25b9d9bbcdb7ffcd4ce3db8cb4a4325f777524b7eb5e6eb923b651fe620d07d6"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.7G"
tar_bytes = 2822632448

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "815M"
zstd_bytes = 854306357

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230629"
previous_tag = "2023-06-29"
previous_file = "kali-xfce_armhf_2023-06-29_13-28-rootfs.tar.zst"
previous_sha256 = "dceeda0314ad47aa2c1ec3783f2870f950493c238b6828d144fc353c7a9f5081"

current_version = "latest02"
current_date = "20230706"
old_file = "kali-xfce_armhf_2023-06-22_13-31-rootfs.tar.zst"
old_sha256 = "f1254bd511443161e1d26c986eff822d08c5b07d35f40b1fdfcfaf880d57a166"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-xfce_armhf_2023-07-06_14-03-rootfs.tar.zst
# SHA256SUM=25b9d9bbcdb7ffcd4ce3db8cb4a4325f777524b7eb5e6eb923b651fe620d07d6
# BUILD_DATE=20230706
# BUILD_TAG=2023-07-06
# STATUS=completed
# VERSION=latest02
# END_TIME=14:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-06
begin = 2023-07-06 12:31:42.648702094+00:00
start-sync_0 = 13:46:35
start-zstd = 13:49:18
start-sync_1 = 14:02:08
end-sync_1 = 14:03:16
end = 2023-07-06 14:03:16.732477645+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabi)'

[port]
tcp = [5902, 36080]
```
