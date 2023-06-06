# ubuntu-lxqt-arm64

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
    --name ubuntu-lxqt-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-lxqt-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-lxqt-arm64 zsh
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

## ubuntu-lxqt-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2023-06-06", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_arm64_2023-06-06_00-54.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "23a93ed361001d82c66c4757cbf0ca2fb06dc3c800cc38f06554b88289c9e079"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4253267968

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1152746778

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230530"
previous_tag = "2023-05-30"
previous_file = "ubuntu-lxqt_arm64_2023-05-30_01-13-rootfs.tar.zst"
previous_sha256 = "ef4f13da5a8cf2051bdfb6123caf686c96ce017b390ef52234161514384b3c91"

current_version = "latest01"
current_date = "20230606"
old_file = "ubuntu-lxqt_arm64_2023-05-23_01-04-rootfs.tar.zst"
old_sha256 = "c1d140f2f9e95b01d8e8286daf252b9e8e88ffaf7ef9cfe83097ece22ab642fc"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-lxqt_arm64_2023-06-06_00-54-rootfs.tar.zst
# SHA256SUM=23a93ed361001d82c66c4757cbf0ca2fb06dc3c800cc38f06554b88289c9e079
# BUILD_DATE=20230606
# BUILD_TAG=2023-06-06
# STATUS=completed
# VERSION=latest01
# END_TIME=00:54

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-06
begin = 2023-06-06 00:03:03.491108598+00:00
start-sync_0 = 00:35:47
start-zstd = 00:39:00
start-sync_1 = 00:53:53
end-sync_1 = 00:54:59
end = 2023-06-06 00:54:59.048771701+00:00

[server]
repo = "cake233/ubuntu-lxqt-arm64"

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
