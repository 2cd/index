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

## alpine-mate-armv7.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2022-02-17"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "alpine-mate_armhf_2022-02-17_00-28.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "27f265dfa18a23650b791384a63a9640c669dfb16493d6feed5197e618a365cc"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "713M"
tar_bytes = 747079680

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "237M"
zstd_bytes = 248316906

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220210"
previous_tag = "2022-02-10"
previous_file = "alpine-mate_armhf_2022-02-10_00-25-rootfs.tar.zst"
previous_sha256 = "fcab918e07de19edfe967433bd50595b5f1dc65cb99669b9dfd0dec4e1c31fa7"

current_version = "latest01"
current_date = "20220217"
old_file = "alpine-mate_armhf_2022-02-03_00-25-rootfs.tar.zst"
old_sha256 = "1643dac50720d050585f3a0975077e5cd6143bffe5b8fc8366b8ffe77bd4d095"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-mate_armhf_2022-02-17_00-28-rootfs.tar.zst
# SHA256SUM=27f265dfa18a23650b791384a63a9640c669dfb16493d6feed5197e618a365cc
# BUILD_DATE=20220217
# BUILD_TAG=2022-02-17
# STATUS=completed
# VERSION=latest01
# END_TIME=00:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-17
begin = 2022-02-17 00:06:23.670120676+00:00
start-sync_0 = 00:25:07
start-zstd = 00:25:51
start-sync_1 = 00:28:20
end-sync_1 = 00:28:41
end = 2022-02-17 00:28:41.578066466+00:00

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (armhf) Version 1.2.2'
zsh = 'zsh 5.8.1 (armv7-alpine-linux-musleabihf)'

[port]
tcp = [5902, 36080]
```
