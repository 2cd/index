# alpine-kde-amd64

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
    --name alpine-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-kde-amd64 zsh
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

## alpine-kde-amd64.toml

```toml
[main]
name = "alpine"
tag = ["kde", "2023-06-15"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-kde_amd64_2023-06-15_00-21.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "17f935483ab10b33b728277a0130d74175b09ec36fb624e5e2bd3c4a97438a03"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1886704128

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "564M"
zstd_bytes = 590663025

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230608"
previous_tag = "2023-06-08"
previous_file = "alpine-kde_amd64_2023-06-08_00-18-rootfs.tar.zst"
previous_sha256 = "843c9e4ffce362f4c965c0a4bc4540a4cc3a0c2317087f4490956d6bd6180bb0"

current_version = "latest02"
current_date = "20230615"
old_file = "alpine-kde_amd64_2023-06-01_00-19-rootfs.tar.zst"
old_sha256 = "6e54c6b0817c79780b7c899c26a7db832b4d7ababecbabf782a4b3746e6518c4"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-kde_amd64_2023-06-15_00-21-rootfs.tar.zst
# SHA256SUM=17f935483ab10b33b728277a0130d74175b09ec36fb624e5e2bd3c4a97438a03
# BUILD_DATE=20230615
# BUILD_TAG=2023-06-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-15
begin = 2023-06-15 00:06:51.859104850+00:00
start-sync_0 = 00:09:57
start-zstd = 00:12:09
start-sync_1 = 00:20:41
end-sync_1 = 00:21:32
end = 2023-06-15 00:21:32.244902664+00:00

[server]
repo = "cake233/alpine-kde-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.4'
zsh = 'zsh 5.9 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
