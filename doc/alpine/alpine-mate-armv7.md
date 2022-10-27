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
tag = ["mate", "2022-10-27"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_armhf_2022-10-27_00-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e42d25640c140b6c4d6c65fb6268041635112e8e2e3ccbc536a94bb3d1157dd1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "684M"
tar_bytes = 716815360

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "221M"
zstd_bytes = 231383649

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221020"
previous_tag = "2022-10-20"
previous_file = "alpine-mate_armhf_2022-10-20_00-11-rootfs.tar.zst"
previous_sha256 = "47bcd08bc56c6562e5e16e4b4a351942295d759b29a2da9acd01bd194736f11a"

current_version = "latest01"
current_date = "20221027"
old_file = "alpine-mate_armhf_2022-10-13_00-12-rootfs.tar.zst"
old_sha256 = "59fc8addd6f4c46238498ea1042a43b72489045260fdedf1b32c9a1351c009fc"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-mate_armhf_2022-10-27_00-12-rootfs.tar.zst
# SHA256SUM=e42d25640c140b6c4d6c65fb6268041635112e8e2e3ccbc536a94bb3d1157dd1
# BUILD_DATE=20221027
# BUILD_TAG=2022-10-27
# STATUS=completed
# VERSION=latest01
# END_TIME=00:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-27
begin = 2022-10-27 00:07:13.095835139+00:00
start-sync_0 = 00:09:20
start-zstd = 00:09:56
start-sync_1 = 00:11:56
end-sync_1 = 00:12:18
end = 2022-10-27 00:12:18.390739250+00:00

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
ldd = 'musl libc (armhf) Version 1.2.3'
zsh = 'zsh 5.9 (armv7-alpine-linux-musleabihf)'

[port]
tcp = [5902, 36080]
```
