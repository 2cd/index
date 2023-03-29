# debian-xfce-arm64

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
    --name debian-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-xfce-arm64 zsh
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

## debian-xfce-arm64.toml

```toml
[main]
name = "debian"
tag = ["xfce", "2023-03-29"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_arm64_2023-03-29_13-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f6e8eb1a16de50453b5c23441de7b833344c741dec0f89c112f8e1bea624075a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4768114176

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1295391643

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230322"
previous_tag = "2023-03-22"
previous_file = "debian-xfce_arm64_2023-03-22_13-10-rootfs.tar.zst"
previous_sha256 = "add66a1efe4f8ce74ac7303cc5df489c2a5f73ba2e52e7e670b59fc1bb9f1651"

current_version = "latest02"
current_date = "20230329"
old_file = "debian-xfce_arm64_2023-03-15_13-15-rootfs.tar.zst"
old_sha256 = "cdab47d3c0993cd8f4b7251a08d0a4c98d89d53e6a7ada1ef5d5890472877f75"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-xfce_arm64_2023-03-29_13-13-rootfs.tar.zst
# SHA256SUM=f6e8eb1a16de50453b5c23441de7b833344c741dec0f89c112f8e1bea624075a
# BUILD_DATE=20230329
# BUILD_TAG=2023-03-29
# STATUS=completed
# VERSION=latest02
# END_TIME=13:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-29
begin = 2023-03-29 12:21:10.228963157+00:00
start-sync_0 = 12:52:04
start-zstd = 12:55:54
start-sync_1 = 13:11:52
end-sync_1 = 13:13:07
end = 2023-03-29 13:13:07.733806931+00:00

[server]
repo = "cake233/debian-xfce-arm64"

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
