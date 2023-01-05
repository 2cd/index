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
tag = ["xfce", "2023-01-05"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_armhf_2023-01-05_13-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7beb69a76f9f060c98d4296c6033a19c4e1ef5833b6827aa8f92b41454e3db03"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3830848000

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1207219750

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221229"
previous_tag = "2022-12-29"
previous_file = "kali-xfce_armhf_2022-12-29_13-05-rootfs.tar.zst"
previous_sha256 = "72a99b746e2c5923d7e022982955e9581326dcc4b3cce5f12103e3e748e28c4c"

current_version = "latest02"
current_date = "20230105"
old_file = "kali-xfce_armhf_2022-12-22_13-14-rootfs.tar.zst"
old_sha256 = "e02d8d9db8afd9ac2b1ce578b7b8b0e9f8ba6612102009d70fd2e1b48356735b"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-xfce_armhf_2023-01-05_13-09-rootfs.tar.zst
# SHA256SUM=7beb69a76f9f060c98d4296c6033a19c4e1ef5833b6827aa8f92b41454e3db03
# BUILD_DATE=20230105
# BUILD_TAG=2023-01-05
# STATUS=completed
# VERSION=latest02
# END_TIME=13:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-05
begin = 2023-01-05 12:19:04.936661641+00:00
start-sync_0 = 12:54:40
start-zstd = 12:57:27
start-sync_1 = 13:08:20
end-sync_1 = 13:09:27
end = 2023-01-05 13:09:27.170552396+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-6) 2.36'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
