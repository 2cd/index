# alpine-mate-386

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not 386, then install qemu & binfmt-support.
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
    --name alpine-mate-386 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-mate-386

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-mate-386 zsh
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

## alpine-mate-386.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2022-07-14"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_i386_2022-07-14_00-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "99559a0ab3180368194cd757c01a38022fb9220c747f6bfd099681aecb8ab953"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "750M"
tar_bytes = 785982464

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "237M"
zstd_bytes = 247513954

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220707"
previous_tag = "2022-07-07"
previous_file = "alpine-mate_i386_2022-07-07_00-27-rootfs.tar.zst"
previous_sha256 = "bf77591f714896ae561ada4aa6ba7efd98895659caba4fc68f4cbdac2dcaa506"

current_version = "latest02"
current_date = "20220714"
old_file = "alpine-mate_i386_2022-06-30_00-30-rootfs.tar.zst"
old_sha256 = "aad5123c2b8b0d7aaad9fd2d0924df0f8f30246c4c8b39a48baac836d145ebd0"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-mate_i386_2022-07-14_00-26-rootfs.tar.zst
# SHA256SUM=99559a0ab3180368194cd757c01a38022fb9220c747f6bfd099681aecb8ab953
# BUILD_DATE=20220714
# BUILD_TAG=2022-07-14
# STATUS=completed
# VERSION=latest02
# END_TIME=00:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-14
begin = 2022-07-14 00:06:25.022100292+00:00
start-sync_0 = 00:23:37
start-zstd = 00:24:15
start-sync_1 = 00:26:20
end-sync_1 = 00:26:39
end = 2022-07-14 00:26:39.300532678+00:00

[server]
repo = "cake233/alpine-mate-386"

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
ldd = 'musl libc (i386) Version 1.2.3'
zsh = 'zsh 5.9 (i586-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
