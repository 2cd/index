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
tag = ["xfce", "2023-06-14"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_arm64_2023-06-14_13-15.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "aa870d6fd7628dab3ca61bbad4bd86cc108a427f9986e4fc8054fc4d74b13f54"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4835720704

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1318079780

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230607"
previous_tag = "2023-06-07"
previous_file = "debian-xfce_arm64_2023-06-07_13-18-rootfs.tar.zst"
previous_sha256 = "ba2571afe2518e81a36a0f8a49dacbe7f165f2512d7e5f763b938bf37a46122f"

current_version = "latest01"
current_date = "20230614"
old_file = "debian-xfce_arm64_2023-05-31_13-22-rootfs.tar.zst"
old_sha256 = "8d91bd5d00974a6e1e4a8352d068eae7f4298668bbe11c86d8b3c6b79856d08c"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-xfce_arm64_2023-06-14_13-15-rootfs.tar.zst
# SHA256SUM=aa870d6fd7628dab3ca61bbad4bd86cc108a427f9986e4fc8054fc4d74b13f54
# BUILD_DATE=20230614
# BUILD_TAG=2023-06-14
# STATUS=completed
# VERSION=latest01
# END_TIME=13:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-14
begin = 2023-06-14 12:22:25.607122898+00:00
start-sync_0 = 12:54:05
start-zstd = 12:57:55
start-sync_1 = 13:14:17
end-sync_1 = 13:15:31
end = 2023-06-14 13:15:31.129433583+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
