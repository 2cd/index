# arch-xfce-armv7

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
    --name arch-xfce-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-armv7 zsh
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

## arch-xfce-armv7.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2023-07-26"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_armhf_2023-07-26_01-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5fff104e7e469cb27b74c667e913c10b8bd18bd258fdbd10b0304ab764a15b1f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.4G"
tar_bytes = 3550049792

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1120837829

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230719"
previous_tag = "2023-07-19"
previous_file = "arch-xfce_armhf_2023-07-19_01-03-rootfs.tar.zst"
previous_sha256 = "695a832798846223357e9b10a5afb8dd58df19bf8f17a0cddd407cff4adcd7a6"

current_version = "latest02"
current_date = "20230726"
old_file = "arch-xfce_armhf_2023-07-12_01-02-rootfs.tar.zst"
old_sha256 = "8723c356ed253bc5ae62bf06b1773b0cf39ad91e4317760fe7229b4a57ef8bbc"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-xfce_armhf_2023-07-26_01-09-rootfs.tar.zst
# SHA256SUM=5fff104e7e469cb27b74c667e913c10b8bd18bd258fdbd10b0304ab764a15b1f
# BUILD_DATE=20230726
# BUILD_TAG=2023-07-26
# STATUS=completed
# VERSION=latest02
# END_TIME=01:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-26
begin = 2023-07-26 00:40:11.186800128+00:00
start-sync_0 = 00:54:03
start-zstd = 00:56:30
start-sync_1 = 01:08:45
end-sync_1 = 01:09:49
end = 2023-07-26 01:09:49.816359504+00:00

[server]
repo = "cake233/arch-xfce-armv7"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (armv7l-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
