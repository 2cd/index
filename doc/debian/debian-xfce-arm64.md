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
tag = ["xfce", "2023-09-20"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_arm64_2023-09-20_14-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6028dd9107628b9ffcf2198717aaacaf29665ccda3b2cb075af99ba373ee4a2a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4884083712

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1311852129

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230913"
previous_tag = "2023-09-13"
previous_file = "debian-xfce_arm64_2023-09-13_13-35-rootfs.tar.zst"
previous_sha256 = "1a57213b7cae2aaeb13cc0d1c12a027ee13900a85e12d533582b5b5d416e0a39"

current_version = "latest02"
current_date = "20230920"
old_file = "debian-xfce_arm64_2023-09-06_13-22-rootfs.tar.zst"
old_sha256 = "59464166f43b962923b1c4fd50a5daaf8eb432666b3fa1246e993c7930333ae9"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-xfce_arm64_2023-09-20_14-14-rootfs.tar.zst
# SHA256SUM=6028dd9107628b9ffcf2198717aaacaf29665ccda3b2cb075af99ba373ee4a2a
# BUILD_DATE=20230920
# BUILD_TAG=2023-09-20
# STATUS=completed
# VERSION=latest02
# END_TIME=14:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-20
begin = 2023-09-20 12:31:47.326051702+00:00
start-sync_0 = 13:50:14
start-zstd = 13:53:53
start-sync_1 = 14:13:02
end-sync_1 = 14:14:26
end = 2023-09-20 14:14:26.685838660+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-10) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
