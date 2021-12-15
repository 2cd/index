# debian-xfce-amd64

## How to run it?

```shell
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
    --name debian-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it debian-xfce-amd64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```shell
    startvnc
```

or

```shell
    startx11vnc
```

or

```shell
    novnc
```

Note:

If you want to use novnc, then open your browser, and type the address:

```
localhost:36081
```

If you want to use tiger/x11vnc, then open vnc viewer, then type the address:

```
localhost:5903
```

## debian-xfce-amd64.toml

```toml
[main]
name = "debian"
tag = ["xfce", "2021-12-15"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "debian-xfce_amd64_2021-12-15_12-40.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "14622a53acd14c968e63d8ea143730ee2c8c75abede78ed7c0eb5ed7e1b6f9f6"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.5G"
tar_bytes = 3661053440

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1006M"
zstd_bytes = 1053899423

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211208"
previous_tag = "2021-12-08"
previous_file = "debian-xfce_amd64_2021-12-08_12-41-rootfs.tar.zst"
previous_sha256 = "91a3bccc9f19ae7d6924f9f57e671badb9a2080721b59075ce43ae18e7fc3ba4"

current_version = "latest01"
current_date = "20211215"
old_file = "debian-xfce_amd64_2021-12-01_12-39-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-xfce_amd64_2021-12-15_12-40-rootfs.tar.zst
# SHA256SUM=14622a53acd14c968e63d8ea143730ee2c8c75abede78ed7c0eb5ed7e1b6f9f6
# BUILD_DATE=20211215
# BUILD_TAG=2021-12-15
# STATUS=completed
# VERSION=latest01
# END_TIME=12:40

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-15
begin = 2021-12-15 12:18:22.818565540+00:00
start-sync_0 = 12:24:59
start-zstd = 12:28:35
start-sync_1 = 12:38:58
end-sync_1 = 12:40:10
end = 2021-12-15 12:40:10.826544665+00:00

[server]
repo = "cake233/debian-xfce-amd64"

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
ldd = 'ldd (Debian GLIBC 2.33-1) 2.33'
zsh = 'zsh 5.8 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
