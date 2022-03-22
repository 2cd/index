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
tag = ["lxqt", "2022-03-22", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "ubuntu-lxqt_arm64_2022-03-22_01-16.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "e7ba267fbed71f533e66454ee7bf0e0ac1fc9ee9a02fa6c510666f7c4ae80b82"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.9G"
tar_bytes = 4106429440

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1021M"
zstd_bytes = 1069921202

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220315"
previous_tag = "2022-03-15"
previous_file = "ubuntu-lxqt_arm64_2022-03-15_01-11-rootfs.tar.zst"
previous_sha256 = "bda5cfac938ecffa72682c31385b7e0690cf6482449d44956a29e93349f67925"

current_version = "latest01"
current_date = "20220322"
old_file = "ubuntu-lxqt_arm64_2022-03-08_01-09-rootfs.tar.zst"
old_sha256 = "58e79f26611a0e74a2f88e99a977c25a4b91d658a68e407bc4ec25597ba8de07"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-lxqt_arm64_2022-03-22_01-16-rootfs.tar.zst
# SHA256SUM=e7ba267fbed71f533e66454ee7bf0e0ac1fc9ee9a02fa6c510666f7c4ae80b82
# BUILD_DATE=20220322
# BUILD_TAG=2022-03-22
# STATUS=completed
# VERSION=latest01
# END_TIME=01:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-22
begin = 2022-03-22 00:21:16.570185182+00:00
start-sync_0 = 00:59:17
start-zstd = 01:03:14
start-sync_1 = 01:15:35
end-sync_1 = 01:16:49
end = 2022-03-22 01:16:49.044290859+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
