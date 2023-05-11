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
tag = ["mate", "2023-05-11"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_armhf_2023-05-11_00-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "faf53b90a7ca15805fb49793aaf1327a2fb01f72e004e9abf319caf6963f7bc1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "954M"
tar_bytes = 999613440

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "352M"
zstd_bytes = 369084259

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230504"
previous_tag = "2023-05-04"
previous_file = "alpine-mate_armhf_2023-05-04_00-14-rootfs.tar.zst"
previous_sha256 = "279e57d1f143c92a99b58889d14f6f260bcaddfa86e41c68a88fa9ca110b6629"

current_version = "latest02"
current_date = "20230511"
old_file = "alpine-mate_armhf_2023-04-27_00-15-rootfs.tar.zst"
old_sha256 = "a8ad648fdf68420ebb631e6ef897a5c472d6abe7facfe0b0618826fabb77a288"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-mate_armhf_2023-05-11_00-12-rootfs.tar.zst
# SHA256SUM=faf53b90a7ca15805fb49793aaf1327a2fb01f72e004e9abf319caf6963f7bc1
# BUILD_DATE=20230511
# BUILD_TAG=2023-05-11
# STATUS=completed
# VERSION=latest02
# END_TIME=00:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-11
begin = 2023-05-11 00:06:02.063226574+00:00
start-sync_0 = 00:08:11
start-zstd = 00:08:56
start-sync_1 = 00:11:58
end-sync_1 = 00:12:23
end = 2023-05-11 00:12:23.780347219+00:00

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
ldd = 'musl libc (armhf) Version 1.2.4'
zsh = 'zsh 5.9 (armv7-alpine-linux-musleabihf)'

[port]
tcp = [5902, 36080]
```
