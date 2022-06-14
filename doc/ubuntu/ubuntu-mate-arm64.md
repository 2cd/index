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
tag = ["mate", "2022-06-14", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-mate_arm64_2022-06-14_01-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "64ed0dbb4d580c0ccd083d1633a4bdc4f04779c8d9d066b79f8edb55cf98c8d8"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.9G"
tar_bytes = 4167524864

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1144670880

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220607"
previous_tag = "2022-06-07"
previous_file = "ubuntu-mate_arm64_2022-06-07_01-22-rootfs.tar.zst"
previous_sha256 = "119308f7f90484330069416225a6058e9ed934c02ae76b5bfe3dde08e6c55c7d"

current_version = "latest01"
current_date = "20220614"
old_file = "ubuntu-mate_arm64_2022-05-31_01-05-rootfs.tar.zst"
old_sha256 = "ceb5b0517be9bea4c2bcc1b85ab4ba0518113cc46a9b803a3839ee5d5a701a2d"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-mate_arm64_2022-06-14_01-13-rootfs.tar.zst
# SHA256SUM=64ed0dbb4d580c0ccd083d1633a4bdc4f04779c8d9d066b79f8edb55cf98c8d8
# BUILD_DATE=20220614
# BUILD_TAG=2022-06-14
# STATUS=completed
# VERSION=latest01
# END_TIME=01:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-14
begin = 2022-06-14 00:19:17.196094549+00:00
start-sync_0 = 00:52:34
start-zstd = 00:56:32
start-sync_1 = 01:11:53
end-sync_1 = 01:13:14
end = 2022-06-14 01:13:14.715664367+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
