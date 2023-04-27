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
tag = ["mate", "2023-04-27"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_i386_2023-04-27_00-23.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1bc3d26bfac83ae5ca43e6899b04d4397dd47517ab2f4ec189bd829ad0e49866"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "733M"
tar_bytes = 768092672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "238M"
zstd_bytes = 249020565

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230420"
previous_tag = "2023-04-20"
previous_file = "alpine-mate_i386_2023-04-20_00-18-rootfs.tar.zst"
previous_sha256 = "65e36847347ad37c7cc0786e3c87b8cb5c61209c5889ca8ab2869e0b7a09023a"

current_version = "latest02"
current_date = "20230427"
old_file = "alpine-mate_i386_2023-04-13_00-18-rootfs.tar.zst"
old_sha256 = "bbe208ac33c8ffbe8fb00b63c110a2ad9f7a792bd0164096b27c3e95d260fd68"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-mate_i386_2023-04-27_00-23-rootfs.tar.zst
# SHA256SUM=1bc3d26bfac83ae5ca43e6899b04d4397dd47517ab2f4ec189bd829ad0e49866
# BUILD_DATE=20230427
# BUILD_TAG=2023-04-27
# STATUS=completed
# VERSION=latest02
# END_TIME=00:23

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-27
begin = 2023-04-27 00:07:01.066036748+00:00
start-sync_0 = 00:19:33
start-zstd = 00:20:45
start-sync_1 = 00:23:29
end-sync_1 = 00:23:53
end = 2023-04-27 00:23:53.359453962+00:00

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
ldd = 'musl libc (i386) Version 1.2.3_git20230424'
zsh = 'zsh 5.9 (i586-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
