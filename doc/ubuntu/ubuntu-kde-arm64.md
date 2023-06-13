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
tag = ["kde", "2023-06-13", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_arm64_2023-06-13_01-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3e5204cb5b3fde97766e3839e49e9b090dd55130b65f06e0d47b38a26fa8719e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.8G"
tar_bytes = 5062466560

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1381782477

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230606"
previous_tag = "2023-06-06"
previous_file = "ubuntu-kde_arm64_2023-06-06_01-05-rootfs.tar.zst"
previous_sha256 = "73a502a642e23e1f834000a0ddfb3f8b1247f3c0b25b0ab8b8439deaf7f61fde"

current_version = "latest02"
current_date = "20230613"
old_file = "ubuntu-kde_arm64_2023-05-30_01-20-rootfs.tar.zst"
old_sha256 = "5691bd8ab2ca45dad80e2bdcb0b36360760d8e9829aa3eef05e01aa6cd12edce"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-kde_arm64_2023-06-13_01-06-rootfs.tar.zst
# SHA256SUM=3e5204cb5b3fde97766e3839e49e9b090dd55130b65f06e0d47b38a26fa8719e
# BUILD_DATE=20230613
# BUILD_TAG=2023-06-13
# STATUS=completed
# VERSION=latest02
# END_TIME=01:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-13
begin = 2023-06-13 00:03:11.270584140+00:00
start-sync_0 = 00:42:39
start-zstd = 00:46:55
start-sync_1 = 01:05:32
end-sync_1 = 01:06:52
end = 2023-06-13 01:06:52.268519313+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
