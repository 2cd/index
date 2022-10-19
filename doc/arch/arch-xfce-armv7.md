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
tag = ["xfce", "2022-10-19"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_armhf_2022-10-19_01-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6c0e517af1042e6c53c73e1570e2b3f574f1ae0d34c3ebceb7b1b6eff5661713"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.2G"
tar_bytes = 3348024832

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1102208404

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221012"
previous_tag = "2022-10-12"
previous_file = "arch-xfce_armhf_2022-10-12_01-00-rootfs.tar.zst"
previous_sha256 = "ff73dfecc0069f4cd874355491ba5ccb931bd70bd0305dc0bcef781452a57ff3"

current_version = "latest01"
current_date = "20221019"
old_file = "arch-xfce_armhf_2022-10-05_01-02-rootfs.tar.zst"
old_sha256 = "16e8ab9cfd1f1edd6b2f09c3b9b677bba454e51d8f8f1055cfe6f8986d559cf5"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-xfce_armhf_2022-10-19_01-06-rootfs.tar.zst
# SHA256SUM=6c0e517af1042e6c53c73e1570e2b3f574f1ae0d34c3ebceb7b1b6eff5661713
# BUILD_DATE=20221019
# BUILD_TAG=2022-10-19
# STATUS=completed
# VERSION=latest01
# END_TIME=01:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-19
begin = 2022-10-19 00:33:08.250746971+00:00
start-sync_0 = 00:48:55
start-zstd = 00:51:49
start-sync_1 = 01:04:58
end-sync_1 = 01:06:12
end = 2022-10-19 01:06:12.439707866+00:00

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
