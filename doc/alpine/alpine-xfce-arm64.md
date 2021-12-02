# alpine-xfce-arm64

## How to run it?

```shell
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
    --name alpine-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it alpine-xfce-arm64 zsh
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

## alpine-xfce-arm64.toml

```toml
[main]
name = "alpine"
tag = ["xfce", "2021-12-02"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "alpine-xfce_arm64_2021-12-02_00-25.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "8b401c9685c0344641d1e7155b70e5b92322fda6d39ae4289ef786523e41f888"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "867M"
tar_bytes = 908614144

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "305M"
zstd_bytes = 319756720

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211130"
last_tag = "2021-11-30"
last_file = "alpine-xfce_arm64_2021-11-30_15-24-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211202"
old_file = "alpine-xfce-arm64_2021-11-28_21-19-rootfs.tar.zst"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-xfce_arm64_2021-12-02_00-25-rootfs.tar.zst
# BUILD_DATE=20211202
# BUILD_TAG=2021-12-02
# STATUS=completed
# VERSION=latest02
# END_TIME=00:25

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-02
begin = 2021-12-02 00:05:47.125939111+00:00
start-sync_0 = 00:21:11
start-zstd = 00:22:02
start-sync_1 = 00:25:00
end-sync_1 = 00:25:27
end = 2021-12-02 00:25:27.414053797+00:00

[server]
repo = "cake233/alpine-xfce-arm64"

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
zsh = 'zsh 5.8 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
