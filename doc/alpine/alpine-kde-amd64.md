# alpine-kde-amd64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not amd64, then install qemu & binfmt-support.
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
    --name alpine-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-kde-amd64 zsh
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

## alpine-kde-amd64.toml

```toml
[main]
name = "alpine"
tag = ["kde", "2023-04-27"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-kde_amd64_2023-04-27_00-19.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3e4c15955ca71b1c3220b10382d7589f7943f2593393c88a1ca931dc6ecc9a37"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1865843200

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "561M"
zstd_bytes = 588148304

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230420"
previous_tag = "2023-04-20"
previous_file = "alpine-kde_amd64_2023-04-20_00-19-rootfs.tar.zst"
previous_sha256 = "5051f8367cd6b128d1185b2b329102f97d6559d0ab2035428ebc8696e4a9cb2d"

current_version = "latest01"
current_date = "20230427"
old_file = "alpine-kde_amd64_2023-04-13_00-13-rootfs.tar.zst"
old_sha256 = "5c32d3cc08538f3e164c6e6a034df9f7035fe0a8468405bacaafe57c058d9fbd"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-kde_amd64_2023-04-27_00-19-rootfs.tar.zst
# SHA256SUM=3e4c15955ca71b1c3220b10382d7589f7943f2593393c88a1ca931dc6ecc9a37
# BUILD_DATE=20230427
# BUILD_TAG=2023-04-27
# STATUS=completed
# VERSION=latest01
# END_TIME=00:19

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-27
begin = 2023-04-27 00:07:00.797907956+00:00
start-sync_0 = 00:09:33
start-zstd = 00:11:23
start-sync_1 = 00:18:34
end-sync_1 = 00:19:22
end = 2023-04-27 00:19:22.881618854+00:00

[server]
repo = "cake233/alpine-kde-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.3_git20230424'
zsh = 'zsh 5.9 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
