# arch-xfce-armv7

## How to run it?

```shell
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

```shell
    docker exex -it arch-xfce-armv7 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```shell
    startvnc
```

or

```shell
    startx11vnc
```

or

```shell
    novnc
```

Note:

If you want to use novnc, then open your browser, and type the address:

```
localhost:36081
```

If you want to use tiger/x11vnc, then open vnc viewer, then type the address:

```
localhost:5903
```

## arch-xfce-armv7.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2021-12-08"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "arch-xfce_armhf_2021-12-08_02-28.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "79c9f05cc84d285f7c809f52a1246f59c23030f6905af7f5ff25c20dd701d430"

# zstd: [1-22]
zstd-level = 15

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.1G"
tar_bytes = 3231662592

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1185448593

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211129"
previous_tag = "2021-11-29"
previous_file = "arch-xfce_armhf_2021-11-29_00-38-rootfs.tar.zst"
previous_sha256 = "bbbaba228ca672ae0026ffd6a42833b1787a205b56b0ed562e273e7150c07e17"

current_version = "latest02"
current_date = "20211208"
old_file = "arch_armhf+xfce-2021_11-03-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-xfce_armhf_2021-12-08_02-28-rootfs.tar.zst
# SHA256SUM=79c9f05cc84d285f7c809f52a1246f59c23030f6905af7f5ff25c20dd701d430
# BUILD_DATE=20211208
# BUILD_TAG=2021-12-08
# STATUS=completed
# VERSION=latest02
# END_TIME=02:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-08
begin = 2021-12-08 01:28:16.788895128+00:00
start-sync_0 = 02:20:58
start-zstd = 02:23:39
start-sync_1 = 02:27:35
end-sync_1 = 02:28:46
end = 2021-12-08 02:28:46.595178394+00:00

[server]
repo = "cake233/arch-xfce-armv7"

[server.node1]
name = "cn"
current = false
previous = true
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
zsh = 'zsh 5.8 (armv7l-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
