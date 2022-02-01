# fedora-mate-arm64

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
    --name fedora-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-arm64 zsh
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

## fedora-mate-arm64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2022-02-01"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "fedora-mate_arm64_2022-02-01_14-12.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "83c444047abb11dbdb80f0069a0ad73e4ccec6e66364273901f3ed7edfe8b5a5"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.8G"
tar_bytes = 6191241728

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1628731925

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220125"
previous_tag = "2022-01-25"
previous_file = "fedora-mate_arm64_2022-01-25_14-13-rootfs.tar.zst"
previous_sha256 = "dd57a6f6939223d34a69da21a09046b3d69b0954cfbc0333a0952e4c80636764"

current_version = "latest01"
current_date = "20220201"
old_file = "fedora-mate_arm64_2022-01-18_14-38-rootfs.tar.zst"
old_sha256 = "b57c22af41fa888337e0281c25ad9d344bbd0e20c8dfba8d8598f73f8856c81a"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-mate_arm64_2022-02-01_14-12-rootfs.tar.zst
# SHA256SUM=83c444047abb11dbdb80f0069a0ad73e4ccec6e66364273901f3ed7edfe8b5a5
# BUILD_DATE=20220201
# BUILD_TAG=2022-02-01
# STATUS=completed
# VERSION=latest01
# END_TIME=14:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-01
begin = 2022-02-01 12:41:34.359109547+00:00
start-sync_0 = 13:48:50
start-zstd = 13:53:55
start-sync_1 = 14:10:51
end-sync_1 = 14:12:26
end = 2022-02-01 14:12:26.287654449+00:00

[server]
repo = "cake233/fedora-mate-arm64"

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
ldd = 'ldd (GNU libc) 2.34.9000'
zsh = 'zsh 5.8 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
