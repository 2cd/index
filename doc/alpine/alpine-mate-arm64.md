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
tag = ["mate", "2022-12-08"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_arm64_2022-12-08_00-24.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2fc4053086f1b0d182fcd94a43e71f29195953fb8670f169cd161498461f1ee0"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1129524224

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "328M"
zstd_bytes = 343571668

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221201"
previous_tag = "2022-12-01"
previous_file = "alpine-mate_arm64_2022-12-01_00-16-rootfs.tar.zst"
previous_sha256 = "73eb40c58554a5425e1ada22d35588156895b1d7498489916e74cbf878e4375d"

current_version = "latest01"
current_date = "20221208"
old_file = "alpine-mate_arm64_2022-11-24_00-14-rootfs.tar.zst"
old_sha256 = "a3cc5ac4acf8a2d6f647ab1aedb43603993e18cd09ff5fcd7536ae3957e61a01"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-mate_arm64_2022-12-08_00-24-rootfs.tar.zst
# SHA256SUM=2fc4053086f1b0d182fcd94a43e71f29195953fb8670f169cd161498461f1ee0
# BUILD_DATE=20221208
# BUILD_TAG=2022-12-08
# STATUS=completed
# VERSION=latest01
# END_TIME=00:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-08
begin = 2022-12-08 00:07:16.450225158+00:00
start-sync_0 = 00:19:22
start-zstd = 00:20:24
start-sync_1 = 00:24:00
end-sync_1 = 00:24:29
end = 2022-12-08 00:24:29.970975964+00:00

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
