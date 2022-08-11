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
tag = ["kde", "2022-08-11"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-kde_amd64_2022-08-11_00-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5b9d5aff684bc68f00a44a27c0214ebbc18e5b3ff2f7e8d966d49703ffa1be30"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1909358592

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "516M"
zstd_bytes = 540928693

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220804"
previous_tag = "2022-08-04"
previous_file = "alpine-kde_amd64_2022-08-04_00-19-rootfs.tar.zst"
previous_sha256 = "4b23cc58687b7477d08155230caaaaecde497138ec148c056ac6fd77295ba9a6"

current_version = "latest01"
current_date = "20220811"
old_file = "alpine-kde_amd64_2022-07-14_00-18-rootfs.tar.zst"
old_sha256 = "543174e188f0c73634ac16cb8284c7757fe43b099a92b93e29f0b666efc35103"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-kde_amd64_2022-08-11_00-17-rootfs.tar.zst
# SHA256SUM=5b9d5aff684bc68f00a44a27c0214ebbc18e5b3ff2f7e8d966d49703ffa1be30
# BUILD_DATE=20220811
# BUILD_TAG=2022-08-11
# STATUS=completed
# VERSION=latest01
# END_TIME=00:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-11
begin = 2022-08-11 00:06:39.237155674+00:00
start-sync_0 = 00:08:34
start-zstd = 00:10:10
start-sync_1 = 00:16:39
end-sync_1 = 00:17:16
end = 2022-08-11 00:17:16.879430374+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.3'
zsh = 'zsh 5.9 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
