# alpine-kde-arm64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
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
    --name alpine-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-kde-arm64 zsh
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

## alpine-kde-arm64.toml

```toml
[main]
name = "alpine"
tag = ["kde", "2023-06-22"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-kde_arm64_2023-06-22_00-23.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "17f8815fc5d2a88ff443cfb294836657f3b4343945d7af34e8ac9fe3781aadbe"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.9G"
tar_bytes = 1942769152

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "553M"
zstd_bytes = 578919787

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230615"
previous_tag = "2023-06-15"
previous_file = "alpine-kde_arm64_2023-06-15_00-24-rootfs.tar.zst"
previous_sha256 = "c7c14fed3db168fa97d2fd15b5d9dddc68c4e849de60f2afcbc2727387ecd4c6"

current_version = "latest01"
current_date = "20230622"
old_file = "alpine-kde_arm64_2023-06-08_00-24-rootfs.tar.zst"
old_sha256 = "65794057aa45a2cc3247848080c02b9f12a586fe5aaa6fdca4938e6a86e28e28"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-kde_arm64_2023-06-22_00-23-rootfs.tar.zst
# SHA256SUM=17f8815fc5d2a88ff443cfb294836657f3b4343945d7af34e8ac9fe3781aadbe
# BUILD_DATE=20230622
# BUILD_TAG=2023-06-22
# STATUS=completed
# VERSION=latest01
# END_TIME=00:23

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-22
begin = 2023-06-22 00:06:11.063009229+00:00
start-sync_0 = 00:14:53
start-zstd = 00:16:18
start-sync_1 = 00:22:33
end-sync_1 = 00:23:11
end = 2023-06-22 00:23:11.251259729+00:00

[server]
repo = "cake233/alpine-kde-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.4'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
