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
tag = ["kde", "2023-07-20"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-kde_arm64_2023-07-20_00-27.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3e96537bfa4c2663e6b9bfb5dd058718643f4121de29eb1ee1a4c51c4cd0ea8f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.9G"
tar_bytes = 1948857856

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "554M"
zstd_bytes = 580159989

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230713"
previous_tag = "2023-07-13"
previous_file = "alpine-kde_arm64_2023-07-13_00-24-rootfs.tar.zst"
previous_sha256 = "def6285606fc41af48a726e8c0a4a9dea1d13e1ad03eafc841d3313aaa6b4644"

current_version = "latest01"
current_date = "20230720"
old_file = "alpine-kde_arm64_2023-07-06_00-30-rootfs.tar.zst"
old_sha256 = "97548686f5303a2d8b517b192c72602ded208e37024d57b8571190285936e171"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-kde_arm64_2023-07-20_00-27-rootfs.tar.zst
# SHA256SUM=3e96537bfa4c2663e6b9bfb5dd058718643f4121de29eb1ee1a4c51c4cd0ea8f
# BUILD_DATE=20230720
# BUILD_TAG=2023-07-20
# STATUS=completed
# VERSION=latest01
# END_TIME=00:27

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-20
begin = 2023-07-20 00:06:33.704589761+00:00
start-sync_0 = 00:17:20
start-zstd = 00:19:03
start-sync_1 = 00:26:37
end-sync_1 = 00:27:19
end = 2023-07-20 00:27:19.648324192+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.4'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
