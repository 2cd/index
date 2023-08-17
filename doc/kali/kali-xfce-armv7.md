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
tag = ["xfce", "2023-08-17"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_armhf_2023-08-17_13-30.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a6ed6c7f7774387c91fac752efc6ce2785212c7a6aedbeb5ff5a338ace335e1c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.8G"
tar_bytes = 2971555840

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "856M"
zstd_bytes = 897305185

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230810"
previous_tag = "2023-08-10"
previous_file = "kali-xfce_armhf_2023-08-10_13-49-rootfs.tar.zst"
previous_sha256 = "3b6c9ffc1ce4b888c4add25f75d4a2de92d17a64cbd524712972d1c4381b84d9"

current_version = "latest02"
current_date = "20230817"
old_file = "kali-xfce_armhf_2023-08-03_13-34-rootfs.tar.zst"
old_sha256 = "ef7651570db5f6513a41ae7750dcaaeb630969fe328ca382f8e885d7135f3ec3"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-xfce_armhf_2023-08-17_13-30-rootfs.tar.zst
# SHA256SUM=a6ed6c7f7774387c91fac752efc6ce2785212c7a6aedbeb5ff5a338ace335e1c
# BUILD_DATE=20230817
# BUILD_TAG=2023-08-17
# STATUS=completed
# VERSION=latest02
# END_TIME=13:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-17
begin = 2023-08-17 12:26:42.911826017+00:00
start-sync_0 = 13:16:52
start-zstd = 13:19:02
start-sync_1 = 13:29:01
end-sync_1 = 13:30:17
end = 2023-08-17 13:30:17.363463404+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-6) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabi)'

[port]
tcp = [5902, 36080]
```
