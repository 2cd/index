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
tag = ["xfce", "2023-03-02"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_arm64_2023-03-02_13-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "dab5a6281d73d5a04b5c54d107143db15ab5eb992ead63fb50f9fc6080b7136c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.9G"
tar_bytes = 5201682944

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1413357022

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230223"
previous_tag = "2023-02-23"
previous_file = "kali-xfce_arm64_2023-02-23_13-27-rootfs.tar.zst"
previous_sha256 = "a386c1708d2ad89e1cee90cb8cc5ba2aa217c479389e77f87ddf76b784682f9a"

current_version = "latest02"
current_date = "20230302"
old_file = "kali-xfce_arm64_2023-02-16_13-37-rootfs.tar.zst"
old_sha256 = "4a7bec901b2ac27f06b95b94cea08ac2ad4c7105c8bc6e27b860f3889554e61f"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2023-03-02_13-28-rootfs.tar.zst
# SHA256SUM=dab5a6281d73d5a04b5c54d107143db15ab5eb992ead63fb50f9fc6080b7136c
# BUILD_DATE=20230302
# BUILD_TAG=2023-03-02
# STATUS=completed
# VERSION=latest02
# END_TIME=13:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-02
begin = 2023-03-02 12:24:50.048032887+00:00
start-sync_0 = 13:05:56
start-zstd = 13:10:04
start-sync_1 = 13:26:35
end-sync_1 = 13:28:00
end = 2023-03-02 13:28:00.670866209+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
