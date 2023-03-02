# alpine-mate-amd64

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
    --name alpine-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-mate-amd64 zsh
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

## alpine-mate-amd64.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2023-03-02"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_amd64_2023-03-02_09-30.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8c9c37c3e9caeb6e89375376ee61cb276bf6d66b152b82b6615ff99625f685d1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1134679552

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "340M"
zstd_bytes = 356226502

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230223"
previous_tag = "2023-02-23"
previous_file = "alpine-mate_amd64_2023-02-23_00-15-rootfs.tar.zst"
previous_sha256 = "8af9170f78165f74d4fb219f29a829c476d2232c107b03441cbfb272f0b4f9cc"

current_version = "latest01"
current_date = "20230302"
old_file = "alpine-mate_amd64_2023-02-16_00-13-rootfs.tar.zst"
old_sha256 = "89ff049c75be2241ab63007d282c665e0cd3298c7fe37d551b3dfe846b41850e"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-mate_amd64_2023-03-02_09-30-rootfs.tar.zst
# SHA256SUM=8c9c37c3e9caeb6e89375376ee61cb276bf6d66b152b82b6615ff99625f685d1
# BUILD_DATE=20230302
# BUILD_TAG=2023-03-02
# STATUS=completed
# VERSION=latest01
# END_TIME=09:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-02
begin = 2023-03-02 09:23:33.383473194+00:00
start-sync_0 = 09:25:36
start-zstd = 09:26:35
start-sync_1 = 09:29:54
end-sync_1 = 09:30:23
end = 2023-03-02 09:30:23.211949935+00:00

[server]
repo = "cake233/alpine-mate-amd64"

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
