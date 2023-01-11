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
tag = ["xfce", "2023-01-11"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_armhf_2023-01-11_01-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "239db2660e515581befe56e3e569f24fc7dd2d7d464e266d706964771f9f5960"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.3G"
tar_bytes = 3440599040

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1110744911

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230104"
previous_tag = "2023-01-04"
previous_file = "arch-xfce_armhf_2023-01-04_01-00-rootfs.tar.zst"
previous_sha256 = "a94cfd007b2850d84531c50034ca522c8e26fa6dd06175e6dce9c21213056574"

current_version = "latest02"
current_date = "20230111"
old_file = "arch-xfce_armhf_2022-12-28_00-55-rootfs.tar.zst"
old_sha256 = "0e369bd605c8cdd4b2e08eb78e5216c83767c8b363119ecf1949d6e8d5ef59ea"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-xfce_armhf_2023-01-11_01-00-rootfs.tar.zst
# SHA256SUM=239db2660e515581befe56e3e569f24fc7dd2d7d464e266d706964771f9f5960
# BUILD_DATE=20230111
# BUILD_TAG=2023-01-11
# STATUS=completed
# VERSION=latest02
# END_TIME=01:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-11
begin = 2023-01-11 00:27:09.864364287+00:00
start-sync_0 = 00:46:08
start-zstd = 00:48:37
start-sync_1 = 00:59:34
end-sync_1 = 01:00:35
end = 2023-01-11 01:00:35.665454198+00:00

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
