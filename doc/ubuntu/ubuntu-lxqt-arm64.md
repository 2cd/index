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

```sh
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
tag = ["lxqt", "2022-02-22", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "ubuntu-lxqt_arm64_2022-02-22_01-15.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "2e7461c1d3a2d814a59b7af7ca6bb36638eeebd04eb1b19abe101d1db9c1ea2b"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3907046400

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "971M"
zstd_bytes = 1017264668

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220215"
previous_tag = "2022-02-15"
previous_file = "ubuntu-lxqt_arm64_2022-02-15_01-06-rootfs.tar.zst"
previous_sha256 = "20fb1133d5488221e5f9f6d347ebac619dbbfa731d5b017251a847c5158784bd"

current_version = "latest01"
current_date = "20220222"
old_file = "ubuntu-lxqt_arm64_2022-02-08_01-08-rootfs.tar.zst"
old_sha256 = "edd93dea9d9b944c197c0eb705a8f3461ad5435295a6eceb6857654a571909a8"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-lxqt_arm64_2022-02-22_01-15-rootfs.tar.zst
# SHA256SUM=2e7461c1d3a2d814a59b7af7ca6bb36638eeebd04eb1b19abe101d1db9c1ea2b
# BUILD_DATE=20220222
# BUILD_TAG=2022-02-22
# STATUS=completed
# VERSION=latest01
# END_TIME=01:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-22
begin = 2022-02-22 00:21:12.697193830+00:00
start-sync_0 = 00:59:18
start-zstd = 01:03:08
start-sync_1 = 01:14:37
end-sync_1 = 01:15:46
end = 2022-02-22 01:15:46.083013307+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu1) 2.35'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
