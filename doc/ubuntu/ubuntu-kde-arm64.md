# ubuntu-kde-arm64

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
    --name ubuntu-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-arm64 zsh
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

## ubuntu-kde-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2024-01-09", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_arm64_2024-01-09_02-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "286eece881cc281de8e890df7fd4a7e7c7d5407b8e0e358cb4d4abfe621c6265"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.4G"
tar_bytes = 5797794304

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1564841980

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231128"
previous_tag = "2023-11-28"
previous_file = "ubuntu-kde_arm64_2023-11-28_01-31-rootfs.tar.zst"
previous_sha256 = "7be07739e590a892d4930d2f8cd54ae4a8b4674470a9e7ad44f2fc684a7f254d"

current_version = "latest02"
current_date = "20240109"
old_file = "ubuntu-kde_arm64_2023-11-21_01-31-rootfs.tar.zst"
old_sha256 = "6794b9c83a7e4fd1410f4af77513be4a37251da16b6b4b2630aa26b79f0e8938"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-kde_arm64_2024-01-09_02-26-rootfs.tar.zst
# SHA256SUM=286eece881cc281de8e890df7fd4a7e7c7d5407b8e0e358cb4d4abfe621c6265
# BUILD_DATE=20240109
# BUILD_TAG=2024-01-09
# STATUS=completed
# VERSION=latest02
# END_TIME=02:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-09
begin = 2024-01-09 00:36:11.823729213+00:00
start-sync_0 = 02:07:56
start-zstd = 02:10:50
start-sync_1 = 02:25:42
end-sync_1 = 02:26:47
end = 2024-01-09 02:26:47.714343325+00:00

[server]
repo = "cake233/ubuntu-kde-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-3ubuntu1) 2.38'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
