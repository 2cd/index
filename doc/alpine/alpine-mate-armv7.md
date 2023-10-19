# alpine-mate-armv7

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
    --name alpine-mate-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-mate-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-mate-armv7 zsh
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

## alpine-mate-armv7.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2023-10-19"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_armhf_2023-10-19_00-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ebf2da1e50f33a3a57281fa5d41510a8ed01d7184b4dba517fc938e4d1e5ef6b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "984M"
tar_bytes = 1030792192

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "360M"
zstd_bytes = 376658465

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231012"
previous_tag = "2023-10-12"
previous_file = "alpine-mate_armhf_2023-10-12_00-13-rootfs.tar.zst"
previous_sha256 = "d537030c0583eb82ee5948c0156911975959615a3b06c40fe676f1568184efd7"

current_version = "latest01"
current_date = "20231019"
old_file = "alpine-mate_armhf_2023-10-05_00-14-rootfs.tar.zst"
old_sha256 = "356a8d6098b2ee119312b934074e4216135cde9434211ad89862605d18d48a38"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-mate_armhf_2023-10-19_00-14-rootfs.tar.zst
# SHA256SUM=ebf2da1e50f33a3a57281fa5d41510a8ed01d7184b4dba517fc938e4d1e5ef6b
# BUILD_DATE=20231019
# BUILD_TAG=2023-10-19
# STATUS=completed
# VERSION=latest01
# END_TIME=00:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-19
begin = 2023-10-19 00:07:01.527879430+00:00
start-sync_0 = 00:10:05
start-zstd = 00:10:53
start-sync_1 = 00:14:20
end-sync_1 = 00:14:55
end = 2023-10-19 00:14:55.671254380+00:00

[server]
repo = "cake233/alpine-mate-armv7"

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (armhf) Version 1.2.4_git20230717'
zsh = 'zsh 5.9 (armv7-alpine-linux-musleabihf)'

[port]
tcp = [5902, 36080]
```
