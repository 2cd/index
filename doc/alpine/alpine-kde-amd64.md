# alpine-kde-amd64

## How to run it?

```sh
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

```sh
    docker exex -it alpine-kde-amd64 zsh
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

## alpine-kde-amd64.toml

```toml
[main]
name = "alpine"
tag = ["kde", "2022-03-17"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "alpine-kde_amd64_2022-03-17_00-19.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "2e2428ea240a2cb1593ca9793d4aba8812415ad80d6f86ef8c8ee66d7200c6e3"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1807914496

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "491M"
zstd_bytes = 514644266

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220310"
previous_tag = "2022-03-10"
previous_file = "alpine-kde_amd64_2022-03-10_00-19-rootfs.tar.zst"
previous_sha256 = "55d6fb4cc6344ac3ef295b6d37b31acfca769af5088ef8ca32e0841c6f011560"

current_version = "latest01"
current_date = "20220317"
old_file = "alpine-kde_amd64_2022-03-03_00-16-rootfs.tar.zst"
old_sha256 = "87299af9ab0d6e99e41a1ecd049b1502161bfdd04a8d358abc8da1154f6ff25d"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-kde_amd64_2022-03-17_00-19-rootfs.tar.zst
# SHA256SUM=2e2428ea240a2cb1593ca9793d4aba8812415ad80d6f86ef8c8ee66d7200c6e3
# BUILD_DATE=20220317
# BUILD_TAG=2022-03-17
# STATUS=completed
# VERSION=latest01
# END_TIME=00:19

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-17
begin = 2022-03-17 00:06:16.353919777+00:00
start-sync_0 = 00:09:04
start-zstd = 00:11:02
start-sync_1 = 00:18:55
end-sync_1 = 00:19:37
end = 2022-03-17 00:19:37.921492762+00:00

[server]
repo = "cake233/alpine-kde-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.2'
zsh = 'zsh 5.8.1 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
