# ubuntu-xfce-arm64

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
    --name ubuntu-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-xfce-arm64 zsh
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

## ubuntu-xfce-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2023-08-08", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_arm64_2023-08-08_00-51.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "02a2825c44a59ba22e797b3153d0c5591d6aa35df62c2a694d46e415c979e809"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3909445632

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1023M"
zstd_bytes = 1072313783

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230801"
previous_tag = "2023-08-01"
previous_file = "ubuntu-xfce_arm64_2023-08-01_00-55-rootfs.tar.zst"
previous_sha256 = "1b0d79a8807b0af7dfe1907c4bfa5c7dcc1741b08294fcad901ff0a8c8b39213"

current_version = "latest02"
current_date = "20230808"
old_file = "ubuntu-xfce_arm64_2023-07-25_01-07-rootfs.tar.zst"
old_sha256 = "b897e713f8dd236f1b4a9c59e8f18a74083667dfe907267f4fa1a6fc07c73fa2"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-xfce_arm64_2023-08-08_00-51-rootfs.tar.zst
# SHA256SUM=02a2825c44a59ba22e797b3153d0c5591d6aa35df62c2a694d46e415c979e809
# BUILD_DATE=20230808
# BUILD_TAG=2023-08-08
# STATUS=completed
# VERSION=latest02
# END_TIME=00:51

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-08
begin = 2023-08-08 00:03:12.520675557+00:00
start-sync_0 = 00:34:36
start-zstd = 00:37:41
start-sync_1 = 00:50:14
end-sync_1 = 00:51:39
end = 2023-08-08 00:51:39.797035576+00:00

[server]
repo = "cake233/ubuntu-xfce-arm64"

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
