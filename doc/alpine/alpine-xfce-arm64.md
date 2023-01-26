# alpine-xfce-arm64

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
    --name alpine-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-xfce-arm64 zsh
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

## alpine-xfce-arm64.toml

```toml
[main]
name = "alpine"
tag = ["xfce", "2023-01-26"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_arm64_2023-01-26_00-19.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3715ae45f7bbfa47307f3d34574a835c2a8b28b0a61ef3760b217c4de2e31a30"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1008M"
tar_bytes = 1056121344

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "330M"
zstd_bytes = 345354759

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230119"
previous_tag = "2023-01-19"
previous_file = "alpine-xfce_arm64_2023-01-19_00-19-rootfs.tar.zst"
previous_sha256 = "9a32b27f7a6b50c896dea5077f49fa1a43675a36f7e6dc3dda7a83883913704c"

current_version = "latest02"
current_date = "20230126"
old_file = "alpine-xfce_arm64_2023-01-12_00-23-rootfs.tar.zst"
old_sha256 = "83c02337851fcd692ea901660408a4598f0d404b5bc1560ef14b20c467853188"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-xfce_arm64_2023-01-26_00-19-rootfs.tar.zst
# SHA256SUM=3715ae45f7bbfa47307f3d34574a835c2a8b28b0a61ef3760b217c4de2e31a30
# BUILD_DATE=20230126
# BUILD_TAG=2023-01-26
# STATUS=completed
# VERSION=latest02
# END_TIME=00:19

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-26
begin = 2023-01-26 00:07:12.047330353+00:00
start-sync_0 = 00:15:23
start-zstd = 00:16:13
start-sync_1 = 00:19:08
end-sync_1 = 00:19:33
end = 2023-01-26 00:19:33.459596543+00:00

[server]
repo = "cake233/alpine-xfce-arm64"

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
