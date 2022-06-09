# alpine-kde-arm64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
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
    --name alpine-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-kde-arm64 zsh
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

## alpine-kde-arm64.toml

```toml
[main]
name = "alpine"
tag = ["kde", "2022-06-09"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-kde_arm64_2022-06-09_00-36.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0682f34862506c2e4bd510ecdd89d0153bd515c80b6daca7220fbab6ac6939ac"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1769766400

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "473M"
zstd_bytes = 495492656

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220602"
previous_tag = "2022-06-02"
previous_file = "alpine-kde_arm64_2022-06-02_00-38-rootfs.tar.zst"
previous_sha256 = "09a4b9d63b724b59502befa9a0fb5dd76a9ca913f8eb3fc5ca5523114a8478ca"

current_version = "latest02"
current_date = "20220609"
old_file = "alpine-kde_arm64_2022-05-26_00-29-rootfs.tar.zst"
old_sha256 = "c17513a1a33fe9fa4803cef3c033240dfd95ed7294a5e7a59bd1692bc4c5a439"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-kde_arm64_2022-06-09_00-36-rootfs.tar.zst
# SHA256SUM=0682f34862506c2e4bd510ecdd89d0153bd515c80b6daca7220fbab6ac6939ac
# BUILD_DATE=20220609
# BUILD_TAG=2022-06-09
# STATUS=completed
# VERSION=latest02
# END_TIME=00:36

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-09
begin = 2022-06-09 00:06:35.872751974+00:00
start-sync_0 = 00:27:12
start-zstd = 00:28:52
start-sync_1 = 00:35:29
end-sync_1 = 00:36:09
end = 2022-06-09 00:36:09.260067733+00:00

[server]
repo = "cake233/alpine-kde-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.3'
zsh = 'zsh 5.8.1 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
