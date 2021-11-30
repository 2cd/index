# alpine-mate-armv7

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
    --name alpine-mate-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-mate-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it alpine-mate-armv7 zsh
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

## alpine-mate-armv7.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2021-11-30"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "alpine-mate_armhf_2021-11-30_15-16.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "899c84839d49239ff0ea5a1b6888b4e234c8fb7d4d3af2fefc190b3823ad2e2f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "707M"
tar_bytes = 740445184

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "236M"
zstd_bytes = 246560351

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211128"
last_tag = "2021-11-28"
last_file = "alpine-mate-armv7_2021-11-28_21-19-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211130"
old_file = "alpine-edge_armhf+mate-2021_10-28-rootfs.tar.zst"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-mate_armhf_2021-11-30_15-16-rootfs.tar.zst
# BUILD_DATE=20211130
# BUILD_TAG=2021-11-30
# STATUS=completed
# VERSION=latest02
# END_TIME=15:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-30
begin = 2021-11-30 15:00:00.802568159+00:00
start-sync_0 = 15:13:51
start-zstd = 15:14:32
start-sync_1 = 15:16:31
end-sync_1 = 15:16:50
end = 2021-11-30 15:16:50.741845517+00:00

[server]
repo = "cake233/alpine-mate-armv7"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "us"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "global"
current = false
last = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "C.UTF-8"

[version]
zsh = 'zsh 5.8 (armv7-alpine-linux-musleabihf)'

[port]
tcp = [5902, 36080]
```
