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
tag = ["mate", "2022-07-21"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_amd64_2022-07-21_00-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fe4fb0c819b9709337157a152a132c70e5c5206aaa688a3668f5bce3d9cf4de1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1103970816

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "328M"
zstd_bytes = 343152409

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220714"
previous_tag = "2022-07-14"
previous_file = "alpine-mate_amd64_2022-07-14_00-13-rootfs.tar.zst"
previous_sha256 = "b61d242d9c9d2244221f2bb5e660c6e48cba2489da0a84a5504956fc51a3a84d"

current_version = "latest02"
current_date = "20220721"
old_file = "alpine-mate_amd64_2022-07-07_00-13-rootfs.tar.zst"
old_sha256 = "d74333316b7e595b1de065cca70b69465922d248db4bc1e81bfc52934b93a5e0"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-mate_amd64_2022-07-21_00-13-rootfs.tar.zst
# SHA256SUM=fe4fb0c819b9709337157a152a132c70e5c5206aaa688a3668f5bce3d9cf4de1
# BUILD_DATE=20220721
# BUILD_TAG=2022-07-21
# STATUS=completed
# VERSION=latest02
# END_TIME=00:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-21
begin = 2022-07-21 00:06:45.136464727+00:00
start-sync_0 = 00:08:49
start-zstd = 00:09:50
start-sync_1 = 00:13:12
end-sync_1 = 00:13:39
end = 2022-07-21 00:13:39.891307298+00:00

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
