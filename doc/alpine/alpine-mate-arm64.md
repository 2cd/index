# alpine-mate-arm64

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
    --name alpine-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it alpine-mate-arm64 zsh
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

## alpine-mate-arm64.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2021-12-09"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "alpine-mate_arm64_2021-12-09_00-31.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "aadb9e1a74a86a621db7483559868c8b484e4d43c96801233b2d945deddd1604"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "986M"
tar_bytes = 1033441792

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "314M"
zstd_bytes = 328960602

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211202"
previous_tag = "2021-12-02"
previous_file = "alpine-mate_arm64_2021-12-02_00-25-rootfs.tar.zst"
previous_sha256 = ""

current_version = "latest02"
current_date = "20211209"
old_file = "alpine-mate_arm64_2021-11-30_15-18-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-mate_arm64_2021-12-09_00-31-rootfs.tar.zst
# SHA256SUM=aadb9e1a74a86a621db7483559868c8b484e4d43c96801233b2d945deddd1604
# BUILD_DATE=20211209
# BUILD_TAG=2021-12-09
# STATUS=completed
# VERSION=latest02
# END_TIME=00:31

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-09
begin = 2021-12-09 00:06:13.610448925+00:00
start-sync_0 = 00:26:23
start-zstd = 00:27:22
start-sync_1 = 00:30:57
end-sync_1 = 00:31:23
end = 2021-12-09 00:31:23.571362861+00:00

[server]
repo = "cake233/alpine-mate-arm64"

[server.node1]
name = "cn"
current = false
previous = true
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
zsh = 'zsh 5.8 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
