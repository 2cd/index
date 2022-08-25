# alpine-xfce-amd64

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
    --name alpine-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-xfce-amd64 zsh
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

## alpine-xfce-amd64.toml

```toml
[main]
name = "alpine"
tag = ["xfce", "2022-08-25"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_amd64_2022-08-25_00-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "bd08611cc586d75360c21d2f2516bc8c8f1186785f28a7bf4989cdcfb115effa"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "970M"
tar_bytes = 1016609280

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "320M"
zstd_bytes = 334635758

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220818"
previous_tag = "2022-08-18"
previous_file = "alpine-xfce_amd64_2022-08-18_00-14-rootfs.tar.zst"
previous_sha256 = "7358a57c946b4912a9015d8d2bf8f98e66736c6afc3c4a437f824625a4a99a54"

current_version = "latest01"
current_date = "20220825"
old_file = "alpine-xfce_amd64_2022-08-11_00-13-rootfs.tar.zst"
old_sha256 = "d0d413e5d06804447f79f9e1f5cd41f4e935ccd54410e9fb89deb1a5f1beb17c"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-xfce_amd64_2022-08-25_00-13-rootfs.tar.zst
# SHA256SUM=bd08611cc586d75360c21d2f2516bc8c8f1186785f28a7bf4989cdcfb115effa
# BUILD_DATE=20220825
# BUILD_TAG=2022-08-25
# STATUS=completed
# VERSION=latest01
# END_TIME=00:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-25
begin = 2022-08-25 00:07:12.776426188+00:00
start-sync_0 = 00:09:19
start-zstd = 00:10:14
start-sync_1 = 00:13:30
end-sync_1 = 00:13:54
end = 2022-08-25 00:13:54.383555441+00:00

[server]
repo = "cake233/alpine-xfce-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.3'
zsh = 'zsh 5.9 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
