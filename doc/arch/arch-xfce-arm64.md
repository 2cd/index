# arch-xfce-arm64

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
    --name arch-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-arm64 zsh
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

## arch-xfce-arm64.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2022-08-17"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_arm64_2022-08-17_01-15.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c09a7d7b97d0bae9b8c59824c849c9c72e531234be614552d416be967e13d00e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4352933376

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1256630850

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220810"
previous_tag = "2022-08-10"
previous_file = "arch-xfce_arm64_2022-08-10_01-09-rootfs.tar.zst"
previous_sha256 = "dee5fdccd07c631cb27bf464c6faf5109a1109aa3b35fda946995d7b805a3dd9"

current_version = "latest02"
current_date = "20220817"
old_file = "arch-xfce_arm64_2022-07-13_01-15-rootfs.tar.zst"
old_sha256 = "13a05cef45dbdc8a5b07e45bb1ac006fb5fca00ac6cf3be2e3ca4d3b12bf856d"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-xfce_arm64_2022-08-17_01-15-rootfs.tar.zst
# SHA256SUM=c09a7d7b97d0bae9b8c59824c849c9c72e531234be614552d416be967e13d00e
# BUILD_DATE=20220817
# BUILD_TAG=2022-08-17
# STATUS=completed
# VERSION=latest02
# END_TIME=01:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-17
begin = 2022-08-17 00:38:16.239909764+00:00
start-sync_0 = 00:55:27
start-zstd = 00:59:11
start-sync_1 = 01:13:49
end-sync_1 = 01:15:04
end = 2022-08-17 01:15:04.192682058+00:00

[server]
repo = "cake233/arch-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
