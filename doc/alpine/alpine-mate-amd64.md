# alpine-mate-amd64

## How to run it?

```shell
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

```shell
    docker exex -it alpine-mate-amd64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```shell
    startvnc
```

or

```shell
    startx11vnc
```

or

```shell
    novnc
```

Note:

If you want to use novnc, then open your browser, and type the address:

```
localhost:36081
```

If you want to use tiger/x11vnc, then open vnc viewer, then type the address:

```
localhost:5903
```

## alpine-mate-amd64.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2021-12-09"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "alpine-mate_amd64_2021-12-09_00-13.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "d83c17d815ee86c9f8e1f422bac75c93fe00e2e8d28a48ea0ee171f93017f51b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1003M"
tar_bytes = 1051385344

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "320M"
zstd_bytes = 334610169

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211202"
previous_tag = "2021-12-02"
previous_file = "alpine-mate_amd64_2021-12-02_00-12-rootfs.tar.zst"
previous_sha256 = ""

current_version = "latest01"
current_date = "20211209"
old_file = "alpine-mate_amd64_2021-11-30_15-06-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-mate_amd64_2021-12-09_00-13-rootfs.tar.zst
# SHA256SUM=d83c17d815ee86c9f8e1f422bac75c93fe00e2e8d28a48ea0ee171f93017f51b
# BUILD_DATE=20211209
# BUILD_TAG=2021-12-09
# STATUS=completed
# VERSION=latest01
# END_TIME=00:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-09
begin = 2021-12-09 00:06:15.302683246+00:00
start-sync_0 = 00:08:27
start-zstd = 00:09:32
start-sync_1 = 00:12:59
end-sync_1 = 00:13:33
end = 2021-12-09 00:13:34.213314252+00:00

[server]
repo = "cake233/alpine-mate-amd64"

[server.node1]
name = "cn"
current = false
previous = true
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
zsh = 'zsh 5.8 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
