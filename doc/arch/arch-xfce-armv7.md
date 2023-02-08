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
tag = ["xfce", "2023-02-08"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_armhf_2023-02-08_01-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4c81a599c2d1dbd6e943857e60bac5482793bbb1eea9d08c6d227d0637e91489"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.3G"
tar_bytes = 3472618496

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1134587877

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230201"
previous_tag = "2023-02-01"
previous_file = "arch-xfce_armhf_2023-02-01_00-59-rootfs.tar.zst"
previous_sha256 = "4d97ccc488f3f8f3c6a7b5c8c6f6bc5bf93a5c8892839b392255416c171bf742"

current_version = "latest01"
current_date = "20230208"
old_file = "arch-xfce_armhf_2023-01-25_01-08-rootfs.tar.zst"
old_sha256 = "f28d73a59feabc455928d63fd7caeab53a878b7902775321ad9790ff62aeac1b"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-xfce_armhf_2023-02-08_01-07-rootfs.tar.zst
# SHA256SUM=4c81a599c2d1dbd6e943857e60bac5482793bbb1eea9d08c6d227d0637e91489
# BUILD_DATE=20230208
# BUILD_TAG=2023-02-08
# STATUS=completed
# VERSION=latest01
# END_TIME=01:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-08
begin = 2023-02-08 00:39:53.422108369+00:00
start-sync_0 = 00:53:10
start-zstd = 00:55:38
start-sync_1 = 01:06:54
end-sync_1 = 01:07:58
end = 2023-02-08 01:07:58.770785157+00:00

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
