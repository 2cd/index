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
tag = ["mate", "2021-12-28"]
os = "fedora"
release = "rawhide"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "fedora-mate_armhf_2021-12-28_13-21.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "d6db1d98ba1d0f65745073a364717b825f3d8efa4a5e257b479bea6bd38e7bee"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.2G"
tar_bytes = 3396981760

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1120442995

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211221"
previous_tag = "2021-12-21"
previous_file = "fedora-mate_armhf_2021-12-21_13-28-rootfs.tar.zst"
previous_sha256 = "beba051348424896225ce0f0e6940bd8abe4798d18e6542fdaaafb38e69bc745"

current_version = "latest02"
current_date = "20211228"
old_file = "fedora-mate_armhf_2021-12-14_13-34-rootfs.tar.zst"
old_sha256 = "dc5bab2ee231a64f0ab1db35d9ee1baca498e2ff3212503806d57d53f549b6fb"
# edition 2021
# DISTRO_NAME=fedora-rawhide_armhf
# ROOTFS_FILE=fedora-mate_armhf_2021-12-28_13-21-rootfs.tar.zst
# SHA256SUM=d6db1d98ba1d0f65745073a364717b825f3d8efa4a5e257b479bea6bd38e7bee
# BUILD_DATE=20211228
# BUILD_TAG=2021-12-28
# STATUS=completed
# VERSION=latest02
# END_TIME=13:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-28
begin = 2021-12-28 12:40:48.323675339+00:00
start-sync_0 = 13:07:46
start-zstd = 13:11:01
start-sync_1 = 13:20:26
end-sync_1 = 13:21:46
end = 2021-12-28 13:21:46.200885526+00:00

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
