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
tag = ["kde", "2022-04-06"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "alpine-kde_amd64_2022-04-06_23-18.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "3aea2b9ad91ffa5fa398759a6d5084f80212a27c0c078fc07613832f919db580"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1809820160

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "492M"
zstd_bytes = 515633448

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220330"
previous_tag = "2022-03-30"
previous_file = "alpine-kde_amd64_2022-03-30_23-17-rootfs.tar.zst"
previous_sha256 = "4b47153e13c54cc53f9b4f6b6e6aeff77e88ba7bfbf3de5d5bdb07661f32c6a2"

current_version = "latest02"
current_date = "20220406"
old_file = "alpine-kde_amd64_2022-03-24_00-19-rootfs.tar.zst"
old_sha256 = "8107254a7727a2cdfbc7f4034763d3ab156f95f3f06eb0fca9fea3c1b9227998"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-kde_amd64_2022-04-06_23-18-rootfs.tar.zst
# SHA256SUM=3aea2b9ad91ffa5fa398759a6d5084f80212a27c0c078fc07613832f919db580
# BUILD_DATE=20220406
# BUILD_TAG=2022-04-06
# STATUS=completed
# VERSION=latest02
# END_TIME=23:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-06
begin = 2022-04-06 23:06:15.665131066+00:00
start-sync_0 = 23:08:38
start-zstd = 23:10:31
start-sync_1 = 23:17:39
end-sync_1 = 23:18:17
end = 2022-04-06 23:18:17.713153736+00:00

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
zsh = 'zsh 5.8.1 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
