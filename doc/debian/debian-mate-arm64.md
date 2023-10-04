# debian-mate-arm64

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
    --name debian-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-mate-arm64 zsh
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

## debian-mate-arm64.toml

```toml
[main]
name = "debian"
tag = ["mate", "2023-10-04"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-mate_arm64_2023-10-04_14-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3759f500bc9d4f28d9b7f6b3ae4ce3ab734da4cae9d0921380de8c7552bec0c1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4811447808

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1255908676

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230927"
previous_tag = "2023-09-27"
previous_file = "debian-mate_arm64_2023-09-27_14-12-rootfs.tar.zst"
previous_sha256 = "b5b0c9931a91dae87fdea8be83690ea4ca3f30545fc2c4676a55a43de90be536"

current_version = "latest02"
current_date = "20231004"
old_file = "debian-mate_arm64_2023-09-20_14-07-rootfs.tar.zst"
old_sha256 = "5242b7a1a5ac4b66b3c80303a75f978564194401cb2ad8627a6bb7b2b6c0f0cd"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-mate_arm64_2023-10-04_14-13-rootfs.tar.zst
# SHA256SUM=3759f500bc9d4f28d9b7f6b3ae4ce3ab734da4cae9d0921380de8c7552bec0c1
# BUILD_DATE=20231004
# BUILD_TAG=2023-10-04
# STATUS=completed
# VERSION=latest02
# END_TIME=14:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-04
begin = 2023-10-04 12:37:42.966362881+00:00
start-sync_0 = 13:49:31
start-zstd = 13:53:28
start-sync_1 = 14:11:43
end-sync_1 = 14:13:10
end = 2023-10-04 14:13:10.600272395+00:00

[server]
repo = "cake233/debian-mate-arm64"

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
