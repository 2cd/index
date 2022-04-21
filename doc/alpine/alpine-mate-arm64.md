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

## alpine-mate-arm64.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2022-04-21"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true
syntax_version = "0.0.0-alpha.3"

[file]
name = "alpine-mate_arm64_2022-04-21_00-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "63fcff0e24c6e0d7e4555716723b62b135b75831281a0a8d2604c49eaea29ab1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1019M"
tar_bytes = 1068128768

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "323M"
zstd_bytes = 337698032

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220414"
previous_tag = "2022-04-14"
previous_file = "alpine-mate_arm64_2022-04-14_00-25-rootfs.tar.zst"
previous_sha256 = "a8330aaee0d78eb38a895aaa9cc2b5aba3e5216b34e216160517d9e24445a50d"

current_version = "latest01"
current_date = "20220421"
old_file = "alpine-mate_arm64_2022-04-10_09-15-rootfs.tar.zst"
old_sha256 = "9ec4950a023f6f3b4c25d28400ff7b4a03c8872e337302d28da856d9bbd10456"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-mate_arm64_2022-04-21_00-28-rootfs.tar.zst
# SHA256SUM=63fcff0e24c6e0d7e4555716723b62b135b75831281a0a8d2604c49eaea29ab1
# BUILD_DATE=20220421
# BUILD_TAG=2022-04-21
# STATUS=completed
# VERSION=latest01
# END_TIME=00:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-21
begin = 2022-04-21 00:06:07.720198245+00:00
start-sync_0 = 00:23:08
start-zstd = 00:24:06
start-sync_1 = 00:27:42
end-sync_1 = 00:28:08
end = 2022-04-21 00:28:08.451462598+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.3'
zsh = 'zsh 5.8.1 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
