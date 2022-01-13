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

```sh
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
tag = ["mate", "2022-01-13"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "alpine-mate_amd64_2022-01-13_00-21.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "ce1802537a0647b44d13eb39615908ae93602d98540334606c5e3b301f5f5aa2"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1005M"
tar_bytes = 1053591040

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "320M"
zstd_bytes = 335445759

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220106"
previous_tag = "2022-01-06"
previous_file = "alpine-mate_amd64_2022-01-06_00-13-rootfs.tar.zst"
previous_sha256 = "5c77efc476dc8bd25c027448720975d68c4de0062a9106efa404f62a8cc7d11c"

current_version = "latest02"
current_date = "20220113"
old_file = "alpine-mate_amd64_2021-12-30_00-13-rootfs.tar.zst"
old_sha256 = "ad17d051df24e995942afeefe12905a652f88a5cb2d0abe1d44c10c7f0dffb65"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-mate_amd64_2022-01-13_00-21-rootfs.tar.zst
# SHA256SUM=ce1802537a0647b44d13eb39615908ae93602d98540334606c5e3b301f5f5aa2
# BUILD_DATE=20220113
# BUILD_TAG=2022-01-13
# STATUS=completed
# VERSION=latest02
# END_TIME=00:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-13
begin = 2022-01-13 00:14:05.256993709+00:00
start-sync_0 = 00:16:11
start-zstd = 00:17:12
start-sync_1 = 00:20:44
end-sync_1 = 00:21:11
end = 2022-01-13 00:21:11.845751664+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.2'
zsh = 'zsh 5.8 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
