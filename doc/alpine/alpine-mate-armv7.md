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
tag = ["mate", "2023-03-23"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_armhf_2023-03-23_00-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "270212967320ddcbcb20728bdee8f93f6cedfee1b603a5096048880574f6e027"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "875M"
tar_bytes = 916647936

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "314M"
zstd_bytes = 328983580

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230316"
previous_tag = "2023-03-16"
previous_file = "alpine-mate_armhf_2023-03-16_00-12-rootfs.tar.zst"
previous_sha256 = "c5858cc9b43680881834442a0a0c77bef33cd655ff554db14ce77be91bc047ea"

current_version = "latest01"
current_date = "20230323"
old_file = "alpine-mate_armhf_2023-03-09_00-12-rootfs.tar.zst"
old_sha256 = "e8665dac8b7e32e44d54bf5cdcb0c72eea21616a08afea639defb873e4e724fd"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-mate_armhf_2023-03-23_00-14-rootfs.tar.zst
# SHA256SUM=270212967320ddcbcb20728bdee8f93f6cedfee1b603a5096048880574f6e027
# BUILD_DATE=20230323
# BUILD_TAG=2023-03-23
# STATUS=completed
# VERSION=latest01
# END_TIME=00:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-23
begin = 2023-03-23 00:07:07.460719406+00:00
start-sync_0 = 00:10:27
start-zstd = 00:11:19
start-sync_1 = 00:14:24
end-sync_1 = 00:14:54
end = 2023-03-23 00:14:54.626730982+00:00

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
ldd = 'musl libc (armhf) Version 1.2.3'
zsh = 'zsh 5.9 (armv7-alpine-linux-musleabihf)'

[port]
tcp = [5902, 36080]
```
