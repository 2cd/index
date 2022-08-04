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
tag = ["kde", "2022-08-04"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-kde_arm64_2022-08-04_00-31.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "77f8a17b732669d5a3bc054f3d75f47aa01f093d20fce198f089c2052f9f148e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1834039808

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "502M"
zstd_bytes = 526002621

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220714"
previous_tag = "2022-07-14"
previous_file = "alpine-kde_arm64_2022-07-14_00-30-rootfs.tar.zst"
previous_sha256 = "76c30a5d958c49fc8402de9577a202d80e410592e8f4758e3fe2ec66fa435139"

current_version = "latest02"
current_date = "20220804"
old_file = "alpine-kde_arm64_2022-07-07_00-37-rootfs.tar.zst"
old_sha256 = "346a3fdf263779549ea1a5e3a1d4012a03d7a265681678cae4acc35683336541"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-kde_arm64_2022-08-04_00-31-rootfs.tar.zst
# SHA256SUM=77f8a17b732669d5a3bc054f3d75f47aa01f093d20fce198f089c2052f9f148e
# BUILD_DATE=20220804
# BUILD_TAG=2022-08-04
# STATUS=completed
# VERSION=latest02
# END_TIME=00:31

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-04
begin = 2022-08-04 00:07:14.564414583+00:00
start-sync_0 = 00:22:31
start-zstd = 00:24:09
start-sync_1 = 00:30:41
end-sync_1 = 00:31:23
end = 2022-08-04 00:31:23.611348802+00:00

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
