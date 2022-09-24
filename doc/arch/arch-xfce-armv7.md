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
tag = ["xfce", "2022-09-24"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_armhf_2022-09-24_05-27.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5e002e4cbf990b7a3ffdf00ad7d632f6ddf20d1e91df85fda39a95c2f2b0de0c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.2G"
tar_bytes = 3362119168

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1100455254

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220907"
previous_tag = "2022-09-07"
previous_file = "arch-xfce_armhf_2022-09-07_01-02-rootfs.tar.zst"
previous_sha256 = "2d6c9ad3b2a21170506b0857d7862a086a7f67ab892b49f77f2f1818109a2b1d"

current_version = "latest02"
current_date = "20220924"
old_file = "arch-xfce_armhf_2022-08-31_01-17-rootfs.tar.zst"
old_sha256 = "9e9c31dfb3e0c293716caaa35992a7d89fb2d181d778bcdb1367fe5d0c315c58"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-xfce_armhf_2022-09-24_05-27-rootfs.tar.zst
# SHA256SUM=5e002e4cbf990b7a3ffdf00ad7d632f6ddf20d1e91df85fda39a95c2f2b0de0c
# BUILD_DATE=20220924
# BUILD_TAG=2022-09-24
# STATUS=completed
# VERSION=latest02
# END_TIME=05:27

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-24
begin = 2022-09-24 04:58:56.671873230+00:00
start-sync_0 = 05:12:13
start-zstd = 05:14:52
start-sync_1 = 05:26:00
end-sync_1 = 05:27:06
end = 2022-09-24 05:27:06.120618234+00:00

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
