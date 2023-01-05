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
tag = ["mate", "2023-01-05"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_amd64_2023-01-05_00-15.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "998e1bcee88f2a4159561e35ca67009644b25e92009ea48d827693c0441f7cba"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1126293504

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "336M"
zstd_bytes = 351619188

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221229"
previous_tag = "2022-12-29"
previous_file = "alpine-mate_amd64_2022-12-29_00-15-rootfs.tar.zst"
previous_sha256 = "9dff9ee7dd6f57d2b4324a1d06bf061bed2c81d1bb100a05c1e6be43a6cd6e2c"

current_version = "latest01"
current_date = "20230105"
old_file = "alpine-mate_amd64_2022-12-22_00-12-rootfs.tar.zst"
old_sha256 = "166745952c3f41cbd67c258c06f540d008fd35788c6222a701a4ff20fa6e92e4"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-mate_amd64_2023-01-05_00-15-rootfs.tar.zst
# SHA256SUM=998e1bcee88f2a4159561e35ca67009644b25e92009ea48d827693c0441f7cba
# BUILD_DATE=20230105
# BUILD_TAG=2023-01-05
# STATUS=completed
# VERSION=latest01
# END_TIME=00:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-05
begin = 2023-01-05 00:07:11.101532841+00:00
start-sync_0 = 00:09:20
start-zstd = 00:10:28
start-sync_1 = 00:14:34
end-sync_1 = 00:15:07
end = 2023-01-05 00:15:07.879080016+00:00

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
