# alpine-mate-armv7

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not armv7, then install qemu & binfmt-support.
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
    --name alpine-mate-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-mate-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-mate-armv7 zsh
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

## alpine-mate-armv7.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2024-01-11"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_armhf_2024-01-11_00-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "396548801de8784ddfec4fe9dcd77933abee73c6acc35a83c8cf37156eb9a265"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1012M"
tar_bytes = 1061060608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "370M"
zstd_bytes = 387909720

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231123"
previous_tag = "2023-11-23"
previous_file = "alpine-mate_armhf_2023-11-23_00-14-rootfs.tar.zst"
previous_sha256 = "4cd0f9630248553e791f45b221f515ab045484b42c4873faaa3d59ee7ffcad27"

current_version = "latest02"
current_date = "20240111"
old_file = "alpine-mate_armhf_2023-11-16_00-13-rootfs.tar.zst"
old_sha256 = "6a078ca8e9d1afb9e8555bfa55eba771307979a932f254e44230b6108afa9124"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-mate_armhf_2024-01-11_00-14-rootfs.tar.zst
# SHA256SUM=396548801de8784ddfec4fe9dcd77933abee73c6acc35a83c8cf37156eb9a265
# BUILD_DATE=20240111
# BUILD_TAG=2024-01-11
# STATUS=completed
# VERSION=latest02
# END_TIME=00:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-11
begin = 2024-01-11 00:08:34.002844534+00:00
start-sync_0 = 00:10:33
start-zstd = 00:11:09
start-sync_1 = 00:13:53
end-sync_1 = 00:14:15
end = 2024-01-11 00:14:15.279110136+00:00

[server]
repo = "cake233/alpine-mate-armv7"

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
ldd = 'musl libc (armhf) Version 1.2.4_git20230717'
zsh = 'zsh 5.9 (armv7-alpine-linux-musleabihf)'

[port]
tcp = [5902, 36080]
```
