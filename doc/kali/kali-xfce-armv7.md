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
tag = ["xfce", "2023-10-19"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_armhf_2023-10-19_13-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "aaabdf70c75278d3b9a9365906fbed58bcc578c439159be5607131b5fa690f44"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.7G"
tar_bytes = 2844583936

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "810M"
zstd_bytes = 848463784

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231012"
previous_tag = "2023-10-12"
previous_file = "kali-xfce_armhf_2023-10-12_13-40-rootfs.tar.zst"
previous_sha256 = "181979b296edd60edd97794effe9e70fd98241c0bb7dddc0c5b16fa4622e87f6"

current_version = "latest01"
current_date = "20231019"
old_file = "kali-xfce_armhf_2023-10-05_13-30-rootfs.tar.zst"
old_sha256 = "050a28de5c5654bc9bf3bf8de428c342b11ca2cf4180a0eccafdeff669545b96"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-xfce_armhf_2023-10-19_13-59-rootfs.tar.zst
# SHA256SUM=aaabdf70c75278d3b9a9365906fbed58bcc578c439159be5607131b5fa690f44
# BUILD_DATE=20231019
# BUILD_TAG=2023-10-19
# STATUS=completed
# VERSION=latest01
# END_TIME=13:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-19
begin = 2023-10-19 12:40:14.981224334+00:00
start-sync_0 = 13:43:38
start-zstd = 13:46:04
start-sync_1 = 13:57:38
end-sync_1 = 13:59:02
end = 2023-10-19 13:59:02.413628423+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabi)'

[port]
tcp = [5902, 36080]
```
