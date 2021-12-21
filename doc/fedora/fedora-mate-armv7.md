# fedora-mate-armv7

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
    --name fedora-mate-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-armv7 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```sh
    startvnc
```

or

```sh
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

## fedora-mate-armv7.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2021-12-21"]
os = "fedora"
release = "rawhide"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "fedora-mate_armhf_2021-12-21_13-28.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "beba051348424896225ce0f0e6940bd8abe4798d18e6542fdaaafb38e69bc745"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.2G"
tar_bytes = 3396737024

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1120391819

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211214"
previous_tag = "2021-12-14"
previous_file = "fedora-mate_armhf_2021-12-14_13-34-rootfs.tar.zst"
previous_sha256 = "dc5bab2ee231a64f0ab1db35d9ee1baca498e2ff3212503806d57d53f549b6fb"

current_version = "latest01"
current_date = "20211221"
old_file = "fedora-mate_armhf_2021-12-07_13-18-rootfs.tar.zst"
old_sha256 = "2e006dbb873d6c6897fc54f6bfec426deb00d1dc91a683901f9e378965476247"
# edition 2021
# DISTRO_NAME=fedora-rawhide_armhf
# ROOTFS_FILE=fedora-mate_armhf_2021-12-21_13-28-rootfs.tar.zst
# SHA256SUM=beba051348424896225ce0f0e6940bd8abe4798d18e6542fdaaafb38e69bc745
# BUILD_DATE=20211221
# BUILD_TAG=2021-12-21
# STATUS=completed
# VERSION=latest01
# END_TIME=13:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-21
begin = 2021-12-21 12:49:11.932626481+00:00
start-sync_0 = 13:14:37
start-zstd = 13:17:39
start-sync_1 = 13:26:53
end-sync_1 = 13:28:09
end = 2021-12-21 13:28:09.043073810+00:00

[server]
repo = "cake233/fedora-mate-armv7"

[server.node1]
name = "cn"
current = false
previous = false
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
ldd = 'ldd (GNU libc) 2.34.9000'
zsh = 'zsh 5.8 (armv7hl-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
