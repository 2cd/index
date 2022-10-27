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
tag = ["xfce", "2022-10-27"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_armhf_2022-10-27_13-15.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2609cd985dcc0335421a0b44cdddee453634bbf45defcf51e1a71288ce36f4a5"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.5G"
tar_bytes = 3733638656

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1193488792

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221020"
previous_tag = "2022-10-20"
previous_file = "kali-xfce_armhf_2022-10-20_13-16-rootfs.tar.zst"
previous_sha256 = "910e3addee24f918eb428c918f434375374e10c1a768f4862ad725b345ac859c"

current_version = "latest02"
current_date = "20221027"
old_file = "kali-xfce_armhf_2022-10-13_13-09-rootfs.tar.zst"
old_sha256 = "5903cc9f76e89e9d904fe3b5a2ac9e72a774c9a2bbe951b1fe3b64eb46f2975a"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-xfce_armhf_2022-10-27_13-15-rootfs.tar.zst
# SHA256SUM=2609cd985dcc0335421a0b44cdddee453634bbf45defcf51e1a71288ce36f4a5
# BUILD_DATE=20221027
# BUILD_TAG=2022-10-27
# STATUS=completed
# VERSION=latest02
# END_TIME=13:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-27
begin = 2022-10-27 12:16:31.879676495+00:00
start-sync_0 = 12:58:33
start-zstd = 13:01:46
start-sync_1 = 13:14:31
end-sync_1 = 13:15:59
end = 2022-10-27 13:15:59.244616937+00:00

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
ldd = 'ldd (Debian GLIBC 2.35-3) 2.35'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
