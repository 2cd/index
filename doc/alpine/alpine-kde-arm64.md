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

## alpine-kde-arm64.toml

```toml
[main]
name = "alpine"
tag = ["kde", "2022-01-27"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "alpine-kde_arm64_2022-01-27_00-36.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "5628d81d012754770966c30e2e7fc2a429cd32c1dfd0f8df57d104da5dc7b8d0"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1778688000

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "538M"
zstd_bytes = 563910663

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220120"
previous_tag = "2022-01-20"
previous_file = "alpine-kde_arm64_2022-01-20_00-31-rootfs.tar.zst"
previous_sha256 = "3023fd1eb71e970311f6fc72c366cd4b598823fe46bbda31825767de141ccab6"

current_version = "latest02"
current_date = "20220127"
old_file = "alpine-kde_arm64_2022-01-06_00-31-rootfs.tar.zst"
old_sha256 = "e4fe5ab872ae6c1e5ef7a6fc3e0a94602103d85dd95ce627c0e64390d7224377"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-kde_arm64_2022-01-27_00-36-rootfs.tar.zst
# SHA256SUM=5628d81d012754770966c30e2e7fc2a429cd32c1dfd0f8df57d104da5dc7b8d0
# BUILD_DATE=20220127
# BUILD_TAG=2022-01-27
# STATUS=completed
# VERSION=latest02
# END_TIME=00:36

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-27
begin = 2022-01-27 00:06:35.194508730+00:00
start-sync_0 = 00:26:19
start-zstd = 00:28:08
start-sync_1 = 00:35:18
end-sync_1 = 00:36:04
end = 2022-01-27 00:36:04.477075853+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.2'
zsh = 'zsh 5.8 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
