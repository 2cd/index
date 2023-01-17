# ubuntu-mate-amd64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not amd64, then install qemu & binfmt-support.
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
    --name ubuntu-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-mate-amd64 zsh
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

## ubuntu-mate-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["mate", "2023-01-17", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-mate_amd64_2023-01-17_00-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a6df10fb2530f67b68ee477c83d05f1ac7fe06feeb6e2a7c0bc011608fa3f473"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4337034752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1160561254

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230110"
previous_tag = "2023-01-10"
previous_file = "ubuntu-mate_amd64_2023-01-10_00-27-rootfs.tar.zst"
previous_sha256 = "50e4c9c3ab7479f7de1f7449b2c8ecd6c2641a4feb7bcaef666e8172bf506491"

current_version = "latest01"
current_date = "20230117"
old_file = "ubuntu-mate_amd64_2023-01-03_00-27-rootfs.tar.zst"
old_sha256 = "37f1a1d811769b91daf3a3476dc3e18fe2f3e5042bb10d1c4c3830ca76366457"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-mate_amd64_2023-01-17_00-28-rootfs.tar.zst
# SHA256SUM=a6df10fb2530f67b68ee477c83d05f1ac7fe06feeb6e2a7c0bc011608fa3f473
# BUILD_DATE=20230117
# BUILD_TAG=2023-01-17
# STATUS=completed
# VERSION=latest01
# END_TIME=00:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-17
begin = 2023-01-17 00:02:59.842312388+00:00
start-sync_0 = 00:09:24
start-zstd = 00:13:09
start-sync_1 = 00:27:38
end-sync_1 = 00:28:47
end = 2023-01-17 00:28:47.693847185+00:00

[server]
repo = "cake233/ubuntu-mate-amd64"

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
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
