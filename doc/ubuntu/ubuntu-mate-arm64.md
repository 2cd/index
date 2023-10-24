# ubuntu-mate-arm64

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
    --name ubuntu-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-mate-arm64 zsh
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

## ubuntu-mate-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["mate", "2023-10-24", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-mate_arm64_2023-10-24_01-42.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4f7b9ae19a7fb8d5dfb9b7158d9e020d3931d92a88ee1581f79f2cca01b80170"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.8G"
tar_bytes = 5079256576

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1332268876

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231017"
previous_tag = "2023-10-17"
previous_file = "ubuntu-mate_arm64_2023-10-17_02-14-rootfs.tar.zst"
previous_sha256 = "5858a035400430e92ffc3c4fba1ad0edd88996f58160a1984456f35ab4cc45a5"

current_version = "latest01"
current_date = "20231024"
old_file = "ubuntu-mate_arm64_2023-10-10_01-40-rootfs.tar.zst"
old_sha256 = "d029398071e4c2b51231cda6f84457425fdbe9f9f23b46bafeccf9eddbe8b445"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-mate_arm64_2023-10-24_01-42-rootfs.tar.zst
# SHA256SUM=4f7b9ae19a7fb8d5dfb9b7158d9e020d3931d92a88ee1581f79f2cca01b80170
# BUILD_DATE=20231024
# BUILD_TAG=2023-10-24
# STATUS=completed
# VERSION=latest01
# END_TIME=01:42

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-24
begin = 2023-10-24 00:28:30.568325459+00:00
start-sync_0 = 01:17:46
start-zstd = 01:21:43
start-sync_1 = 01:41:14
end-sync_1 = 01:42:42
end = 2023-10-24 01:42:42.372879573+00:00

[server]
repo = "cake233/ubuntu-mate-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu6) 2.38'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
