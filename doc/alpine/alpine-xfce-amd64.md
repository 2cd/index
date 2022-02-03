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

## alpine-xfce-amd64.toml

```toml
[main]
name = "alpine"
tag = ["xfce", "2022-02-03"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "alpine-xfce_amd64_2022-02-03_00-13.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "5addb01df53ae64fe96f403c0d6d3be364ab2dacd3226c89b99033c303b305e3"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "884M"
tar_bytes = 926523392

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "325M"
zstd_bytes = 340390366

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220127"
previous_tag = "2022-01-27"
previous_file = "alpine-xfce_amd64_2022-01-27_00-14-rootfs.tar.zst"
previous_sha256 = "3d7fdee6711e46909d31f63a452feec11391401c6e22630f77c0981bc91284eb"

current_version = "latest01"
current_date = "20220203"
old_file = "alpine-xfce_amd64_2022-01-20_00-15-rootfs.tar.zst"
old_sha256 = "7e822c40a5899cb4a45c89a2eca9feab257e983050ff94e88b31ce23a3b7c338"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-xfce_amd64_2022-02-03_00-13-rootfs.tar.zst
# SHA256SUM=5addb01df53ae64fe96f403c0d6d3be364ab2dacd3226c89b99033c303b305e3
# BUILD_DATE=20220203
# BUILD_TAG=2022-02-03
# STATUS=completed
# VERSION=latest01
# END_TIME=00:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-03
begin = 2022-02-03 00:06:33.276829846+00:00
start-sync_0 = 00:09:27
start-zstd = 00:10:24
start-sync_1 = 00:13:32
end-sync_1 = 00:13:58
end = 2022-02-03 00:13:58.790792741+00:00

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
