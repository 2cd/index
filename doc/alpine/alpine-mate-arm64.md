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
tag = ["mate", "2022-02-24"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "alpine-mate_arm64_2022-02-24_00-28.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "d798dc850511fda6fc63510161b2a7d25679714a98724595f131a6ddd6547bc1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "999M"
tar_bytes = 1047031808

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "318M"
zstd_bytes = 332548905

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220217"
previous_tag = "2022-02-17"
previous_file = "alpine-mate_arm64_2022-02-17_00-27-rootfs.tar.zst"
previous_sha256 = "10d692df779572dfc0d9cdeb56378e32965f591299bde7109c4e25b6e796bb3d"

current_version = "latest02"
current_date = "20220224"
old_file = "alpine-mate_arm64_2022-02-10_00-26-rootfs.tar.zst"
old_sha256 = "b572faad0ea2f5255482750df7871e4e3743358a866316ea8840560fe079a161"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-mate_arm64_2022-02-24_00-28-rootfs.tar.zst
# SHA256SUM=d798dc850511fda6fc63510161b2a7d25679714a98724595f131a6ddd6547bc1
# BUILD_DATE=20220224
# BUILD_TAG=2022-02-24
# STATUS=completed
# VERSION=latest02
# END_TIME=00:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-24
begin = 2022-02-24 00:06:47.551113377+00:00
start-sync_0 = 00:23:44
start-zstd = 00:24:36
start-sync_1 = 00:28:15
end-sync_1 = 00:28:41
end = 2022-02-24 00:28:41.775000276+00:00

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
zsh = 'zsh 5.8.1 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
