# alpine-kde-amd64

## How to run it?

```shell
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not amd64, then install qemu & binfmt-support.
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
    --name alpine-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it alpine-kde-amd64 zsh
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

## alpine-kde-amd64.toml

```toml
[main]
name = "alpine"
tag = ["kde", "2021-12-02"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "alpine-kde_amd64_2021-12-02_00-17.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "2206e79e1178f6cc321fb711a2df287277c9f06d1d98b5841a1b37a8452f9b91"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1819364352

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "549M"
zstd_bytes = 575609816

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211130"
previous_tag = "2021-11-30"
previous_file = "alpine-kde_amd64_2021-11-30_15-13-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211202"
old_file = "alpine-kde-amd64_2021-11-28_21-09-rootfs.tar.zst"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-kde_amd64_2021-12-02_00-17-rootfs.tar.zst
# BUILD_DATE=20211202
# BUILD_TAG=2021-12-02
# STATUS=completed
# VERSION=latest02
# END_TIME=00:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-02
begin = 2021-12-02 00:05:45.996381581+00:00
start-sync_0 = 00:08:25
start-zstd = 00:10:05
start-sync_1 = 00:16:25
end-sync_1 = 00:17:06
end = 2021-12-02 00:17:06.180205546+00:00

[server]
repo = "cake233/alpine-kde-amd64"

[server.node1]
name = "cn"
current = false
previous = true
in_sync = false
split = false

[server.node2]
name = "us"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "global"
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
zsh = 'zsh 5.8 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
