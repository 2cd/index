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
tag = ["xfce", "2022-05-17", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_arm64_2022-05-17_01-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d925acd828567249338a6b62c591c9f50864c90483065789097b5adfcac6b6a8"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.4G"
tar_bytes = 3571429376

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "940M"
zstd_bytes = 985480105

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220510"
previous_tag = "2022-05-10"
previous_file = "ubuntu-xfce_arm64_2022-05-10_01-27-rootfs.tar.zst"
previous_sha256 = "469dccac4e90808e685245ce5b2ca7ec4b3582ec3e85d771b285dcd50d1811d6"

current_version = "latest02"
current_date = "20220517"
old_file = "ubuntu-xfce_arm64_2022-05-03_01-01-rootfs.tar.zst"
old_sha256 = "c0c0bc7fcd05490564dc92aa99ce9e2626461734d41d3b74eadf5e5d4c8029dd"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-xfce_arm64_2022-05-17_01-06-rootfs.tar.zst
# SHA256SUM=d925acd828567249338a6b62c591c9f50864c90483065789097b5adfcac6b6a8
# BUILD_DATE=20220517
# BUILD_TAG=2022-05-17
# STATUS=completed
# VERSION=latest02
# END_TIME=01:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-17
begin = 2022-05-17 00:21:30.738733676+00:00
start-sync_0 = 00:51:05
start-zstd = 00:53:52
start-sync_1 = 01:05:42
end-sync_1 = 01:06:47
end = 2022-05-17 01:06:48.007283048+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
