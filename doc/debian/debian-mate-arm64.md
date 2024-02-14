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
tag = ["mate", "2024-02-14"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-mate_arm64_2024-02-14_14-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3cebc3fd6525797f8d33f41bfb3ee0e85f2125cb879e03098a11a9d3e7dd270c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4937954816

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1281372578

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-mate_arm64_2023-11-22_13-50-rootfs.tar.zst"
previous_sha256 = "60859ea968113c1f31b102e01cd59379076a0dc72f276f0bc4f3347835ba96c1"

current_version = "latest01"
current_date = "20240214"
old_file = "debian-mate_arm64_2023-11-15_13-54-rootfs.tar.zst"
old_sha256 = "7809207b2ed7760cc5a304a2b54acfc41cb074a34c7edef6930f721b010569ce"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-mate_arm64_2024-02-14_14-03-rootfs.tar.zst
# SHA256SUM=3cebc3fd6525797f8d33f41bfb3ee0e85f2125cb879e03098a11a9d3e7dd270c
# BUILD_DATE=20240214
# BUILD_TAG=2024-02-14
# STATUS=completed
# VERSION=latest01
# END_TIME=14:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-14
begin = 2024-02-14 12:33:41.206961821+00:00
start-sync_0 = 13:48:44
start-zstd = 13:51:11
start-sync_1 = 14:02:49
end-sync_1 = 14:03:49
end = 2024-02-14 14:03:49.760068707+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-15) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
