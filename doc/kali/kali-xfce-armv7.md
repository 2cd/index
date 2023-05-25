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
tag = ["xfce", "2023-05-25"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_armhf_2023-05-25_13-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "801277ef28c5a64a0ccaef873f76f20a720e0461d9a506a757738e4a13d2401b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.7G"
tar_bytes = 2826500608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "814M"
zstd_bytes = 853421576

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230504"
previous_tag = "2023-05-04"
previous_file = "kali-xfce_armhf_2023-05-04_13-45-rootfs.tar.zst"
previous_sha256 = "927c99e7825466b93b639a8710af046bd9a97e0980dfb4e734d975fc88757c26"

current_version = "latest02"
current_date = "20230525"
old_file = "kali-xfce_armhf_2023-04-27_13-28-rootfs.tar.zst"
old_sha256 = "24cd5223e2830df6ab9f9246ce8f2bd9d98de467f8874f4bdea652071e4c5c2a"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-xfce_armhf_2023-05-25_13-28-rootfs.tar.zst
# SHA256SUM=801277ef28c5a64a0ccaef873f76f20a720e0461d9a506a757738e4a13d2401b
# BUILD_DATE=20230525
# BUILD_TAG=2023-05-25
# STATUS=completed
# VERSION=latest02
# END_TIME=13:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-25
begin = 2023-05-25 12:24:40.477225671+00:00
start-sync_0 = 13:15:21
start-zstd = 13:17:16
start-sync_1 = 13:27:14
end-sync_1 = 13:28:08
end = 2023-05-25 13:28:08.192380622+00:00

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
