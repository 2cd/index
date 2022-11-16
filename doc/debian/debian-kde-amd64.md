# debian-kde-amd64

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
    --name debian-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-kde-amd64 zsh
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

## debian-kde-amd64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2022-11-16"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_amd64_2022-11-16_12-54.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "535d2fe6fa97e283a95d4137d634ea96ee28fee9ed4552a4096da0f81746c4f8"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.4G"
tar_bytes = 5724851200

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1624921851

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221109"
previous_tag = "2022-11-09"
previous_file = "debian-kde_amd64_2022-11-09_12-54-rootfs.tar.zst"
previous_sha256 = "96b628c8d545a6d71ed3adae7beb2d2b687f7671ae0e8a742160ff3a6f1e820f"

current_version = "latest01"
current_date = "20221116"
old_file = "debian-kde_amd64_2022-11-02_12-54-rootfs.tar.zst"
old_sha256 = "dba4df9514b2e292e4f49c3043769fd242d00976a182f1f8f5b79156a0363052"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-kde_amd64_2022-11-16_12-54-rootfs.tar.zst
# SHA256SUM=535d2fe6fa97e283a95d4137d634ea96ee28fee9ed4552a4096da0f81746c4f8
# BUILD_DATE=20221116
# BUILD_TAG=2022-11-16
# STATUS=completed
# VERSION=latest01
# END_TIME=12:54

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-16
begin = 2022-11-16 12:21:31.346331602+00:00
start-sync_0 = 12:28:30
start-zstd = 12:33:42
start-sync_1 = 12:52:58
end-sync_1 = 12:54:25
end = 2022-11-16 12:54:25.262265180+00:00

[server]
repo = "cake233/debian-kde-amd64"

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
ldd = 'ldd (Debian GLIBC 2.36-5) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
