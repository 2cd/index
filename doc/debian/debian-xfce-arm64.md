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
tag = ["xfce", "2023-02-15"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_arm64_2023-02-15_13-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "da9061f2ffa7bf9df3d00965b60d13d0ea8ac029c3255bea73ab7b0d1078e291"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4390124032

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1193962638

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230208"
previous_tag = "2023-02-08"
previous_file = "debian-xfce_arm64_2023-02-08_13-14-rootfs.tar.zst"
previous_sha256 = "00150f33c485118195e7549ff1458a51304f927c6a8a2646263b45025c121d7b"

current_version = "latest02"
current_date = "20230215"
old_file = "debian-xfce_arm64_2023-02-01_13-19-rootfs.tar.zst"
old_sha256 = "3fbd125119de6d72eecb322572f371a1599c1b72659aa83c53e6d4afab673fbd"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-xfce_arm64_2023-02-15_13-14-rootfs.tar.zst
# SHA256SUM=da9061f2ffa7bf9df3d00965b60d13d0ea8ac029c3255bea73ab7b0d1078e291
# BUILD_DATE=20230215
# BUILD_TAG=2023-02-15
# STATUS=completed
# VERSION=latest02
# END_TIME=13:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-15
begin = 2023-02-15 12:27:11.194306841+00:00
start-sync_0 = 12:56:26
start-zstd = 12:59:39
start-sync_1 = 13:13:23
end-sync_1 = 13:14:27
end = 2023-02-15 13:14:28.018980210+00:00

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
