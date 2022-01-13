# alpine-mate-arm64

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
    --name alpine-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-mate-arm64 zsh
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

## alpine-mate-arm64.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2022-01-13"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "alpine-mate_arm64_2022-01-13_00-40.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "2b5aa44ec67e77b31133e86231ac2c740cff6bce5647de64dd314cacab8902a9"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "988M"
tar_bytes = 1035552768

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "315M"
zstd_bytes = 329777484

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220106"
previous_tag = "2022-01-06"
previous_file = "alpine-mate_arm64_2022-01-06_00-27-rootfs.tar.zst"
previous_sha256 = "e2d655638ab87f20dc716f14f966361537e8b06213f68289caf1e8bd9c0f5dd8"

current_version = "latest01"
current_date = "20220113"
old_file = "alpine-mate_arm64_2021-12-30_00-26-rootfs.tar.zst"
old_sha256 = "f920bc0964f46c98c3f9f1a389468b448fa46da06474db10f43bb74ecd7371f0"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-mate_arm64_2022-01-13_00-40-rootfs.tar.zst
# SHA256SUM=2b5aa44ec67e77b31133e86231ac2c740cff6bce5647de64dd314cacab8902a9
# BUILD_DATE=20220113
# BUILD_TAG=2022-01-13
# STATUS=completed
# VERSION=latest01
# END_TIME=00:40

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-13
begin = 2022-01-13 00:14:12.138804400+00:00
start-sync_0 = 00:35:16
start-zstd = 00:36:20
start-sync_1 = 00:39:47
end-sync_1 = 00:40:17
end = 2022-01-13 00:40:17.942781742+00:00

[server]
repo = "cake233/alpine-mate-arm64"

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
