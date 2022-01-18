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

## ubuntu-xfce-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2022-01-18", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "ubuntu-xfce_arm64_2022-01-18_01-18.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "abfadd5150651533a95994a03d9050292f142b9cd8377691a322c6fbaacd655e"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.4G"
tar_bytes = 3558107648

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "895M"
zstd_bytes = 937790297

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220111"
previous_tag = "2022-01-11"
previous_file = "ubuntu-xfce_arm64_2022-01-11_01-15-rootfs.tar.zst"
previous_sha256 = "958111e7406d325b16eb2846a56ec39d3953b2bcd86838299abb7bc4c91a27e3"

current_version = "latest02"
current_date = "20220118"
old_file = "ubuntu-xfce_arm64_2022-01-04_01-11-rootfs.tar.zst"
old_sha256 = "dfe904a3681ead609da4ac3b48b9d059cbf83e0cb1a30a7c72fe44d9fa5db1cb"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-xfce_arm64_2022-01-18_01-18-rootfs.tar.zst
# SHA256SUM=abfadd5150651533a95994a03d9050292f142b9cd8377691a322c6fbaacd655e
# BUILD_DATE=20220118
# BUILD_TAG=2022-01-18
# STATUS=completed
# VERSION=latest02
# END_TIME=01:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-18
begin = 2022-01-18 00:19:17.098256133+00:00
start-sync_0 = 01:02:28
start-zstd = 01:06:05
start-sync_1 = 01:16:54
end-sync_1 = 01:18:06
end = 2022-01-18 01:18:06.313232183+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.34-0ubuntu3) 2.34'
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
