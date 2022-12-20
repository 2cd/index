# fedora-xfce-arm64

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
    --name fedora-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-xfce-arm64 zsh
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

## fedora-xfce-arm64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2022-12-20"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_arm64_2022-12-20_14-33.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "554844ec866c59f3db2a2a5d2ce0130f7f77b428abeebdce23df0002822f6b5e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.7G"
tar_bytes = 6032262144

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1621894808

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221213"
previous_tag = "2022-12-13"
previous_file = "fedora-xfce_arm64_2022-12-13_14-11-rootfs.tar.zst"
previous_sha256 = "965f4fffbc9a7e0468000b17e63e7651deff1b5b0a46fd8e8f8b0726afbab546"

current_version = "latest02"
current_date = "20221220"
old_file = "fedora-xfce_arm64_2022-12-06_14-15-rootfs.tar.zst"
old_sha256 = "072c05e06fed16a93fb75ea9b426fecf4a957bc8baac512a764e06f62afc4201"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-xfce_arm64_2022-12-20_14-33-rootfs.tar.zst
# SHA256SUM=554844ec866c59f3db2a2a5d2ce0130f7f77b428abeebdce23df0002822f6b5e
# BUILD_DATE=20221220
# BUILD_TAG=2022-12-20
# STATUS=completed
# VERSION=latest02
# END_TIME=14:33

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-20
begin = 2022-12-20 12:49:14.035289675+00:00
start-sync_0 = 14:05:25
start-zstd = 14:11:06
start-sync_1 = 14:31:52
end-sync_1 = 14:33:32
end = 2022-12-20 14:33:32.513280710+00:00

[server]
repo = "cake233/fedora-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
