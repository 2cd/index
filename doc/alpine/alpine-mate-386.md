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
tag = ["mate", "2023-06-22"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_i386_2023-06-22_00-21.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "dbcac10fc1cdc7b53f7e460915ab8d59725fdf569bd18b058e84407d3f072898"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "720M"
tar_bytes = 754248192

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "236M"
zstd_bytes = 246579223

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230615"
previous_tag = "2023-06-15"
previous_file = "alpine-mate_i386_2023-06-15_00-19-rootfs.tar.zst"
previous_sha256 = "bbd45b03325aca35c29d30eccc4bbb237eb7fc9ed15eaf923a1e68835b31482c"

current_version = "latest02"
current_date = "20230622"
old_file = "alpine-mate_i386_2023-06-08_00-18-rootfs.tar.zst"
old_sha256 = "8d44ee459a89f5d16781c916eebce0fe745543ee07b193459f4e5044c7745bd1"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-mate_i386_2023-06-22_00-21-rootfs.tar.zst
# SHA256SUM=dbcac10fc1cdc7b53f7e460915ab8d59725fdf569bd18b058e84407d3f072898
# BUILD_DATE=20230622
# BUILD_TAG=2023-06-22
# STATUS=completed
# VERSION=latest02
# END_TIME=00:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-22
begin = 2023-06-22 00:06:20.559305179+00:00
start-sync_0 = 00:17:07
start-zstd = 00:17:53
start-sync_1 = 00:20:42
end-sync_1 = 00:21:06
end = 2023-06-22 00:21:06.595180984+00:00

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
ldd = 'musl libc (i386) Version 1.2.4'
zsh = 'zsh 5.9 (i586-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
