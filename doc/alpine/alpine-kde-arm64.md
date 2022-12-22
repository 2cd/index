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
tag = ["kde", "2022-12-22"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-kde_arm64_2022-12-22_00-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fc9c23ea7085f933071684892eb6dc3320a5340335991fe677f9ed4ca4fdb085"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1904824320

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "517M"
zstd_bytes = 541696842

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221215"
previous_tag = "2022-12-15"
previous_file = "alpine-kde_arm64_2022-12-15_00-24-rootfs.tar.zst"
previous_sha256 = "55d471faa94e7b56b95cc31b9102d46d1e6e28acce2e68cc7db027d55b1e9fd9"

current_version = "latest01"
current_date = "20221222"
old_file = "alpine-kde_arm64_2022-12-08_00-28-rootfs.tar.zst"
old_sha256 = "81047380b2d36f3984fcaa8bafa7bf922aeacfb5001363e193cc09d7a7e2744f"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-kde_arm64_2022-12-22_00-29-rootfs.tar.zst
# SHA256SUM=fc9c23ea7085f933071684892eb6dc3320a5340335991fe677f9ed4ca4fdb085
# BUILD_DATE=20221222
# BUILD_TAG=2022-12-22
# STATUS=completed
# VERSION=latest01
# END_TIME=00:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-22
begin = 2022-12-22 00:06:25.924128937+00:00
start-sync_0 = 00:19:50
start-zstd = 00:21:38
start-sync_1 = 00:28:48
end-sync_1 = 00:29:30
end = 2022-12-22 00:29:30.481302240+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.3'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
