# kali-xfce-arm64

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
    --name kali-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-arm64 zsh
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

## kali-xfce-arm64.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2024-01-25"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_arm64_2024-01-25_14-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "65f34cf66fcc4a496d6d35efed7fb009ac062ccdba6cebb92fa67ad3d3f02ff1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.1G"
tar_bytes = 5403440128

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1467928751

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231123"
previous_tag = "2023-11-23"
previous_file = "kali-xfce_arm64_2023-11-23_14-14-rootfs.tar.zst"
previous_sha256 = "a30b80d59b73f8a22bd31c413a52f533c48a37b6e4c151e754e157677731403e"

current_version = "latest01"
current_date = "20240125"
old_file = "kali-xfce_arm64_2023-11-16_14-11-rootfs.tar.zst"
old_sha256 = "737a22bc1354df9978f81fc124bf917bde85caa25346714c9ae7558ebf3f4dde"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2024-01-25_14-12-rootfs.tar.zst
# SHA256SUM=65f34cf66fcc4a496d6d35efed7fb009ac062ccdba6cebb92fa67ad3d3f02ff1
# BUILD_DATE=20240125
# BUILD_TAG=2024-01-25
# STATUS=completed
# VERSION=latest01
# END_TIME=14:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-25
begin = 2024-01-25 12:30:16.169029041+00:00
start-sync_0 = 13:54:29
start-zstd = 13:57:12
start-sync_1 = 14:11:35
end-sync_1 = 14:12:45
end = 2024-01-25 14:12:45.044481897+00:00

[server]
repo = "cake233/kali-xfce-arm64"

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
