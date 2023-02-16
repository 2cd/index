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
tag = ["mate", "2023-02-16"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_amd64_2023-02-16_00-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "89ff049c75be2241ab63007d282c665e0cd3298c7fe37d551b3dfe846b41850e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1131890176

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "339M"
zstd_bytes = 354959884

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230209"
previous_tag = "2023-02-09"
previous_file = "alpine-mate_amd64_2023-02-09_00-13-rootfs.tar.zst"
previous_sha256 = "9ac56fc07cdf9e861b913b11520cc95cc58c6ccd24350b542aa9dfb118d3de5e"

current_version = "latest01"
current_date = "20230216"
old_file = "alpine-mate_amd64_2023-02-02_00-12-rootfs.tar.zst"
old_sha256 = "f459d19433aa34ab0685c3cf41fa9d63d12ce89a07847efd0e30862dceb59bba"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-mate_amd64_2023-02-16_00-13-rootfs.tar.zst
# SHA256SUM=89ff049c75be2241ab63007d282c665e0cd3298c7fe37d551b3dfe846b41850e
# BUILD_DATE=20230216
# BUILD_TAG=2023-02-16
# STATUS=completed
# VERSION=latest01
# END_TIME=00:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-16
begin = 2023-02-16 00:07:08.879526803+00:00
start-sync_0 = 00:08:43
start-zstd = 00:09:40
start-sync_1 = 00:13:06
end-sync_1 = 00:13:29
end = 2023-02-16 00:13:29.778135556+00:00

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
