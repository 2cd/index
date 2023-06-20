# ubuntu-lxqt-amd64

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
    --name ubuntu-lxqt-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-lxqt-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-lxqt-amd64 zsh
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

## ubuntu-lxqt-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2023-06-20", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_amd64_2023-06-20_00-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b41d831063b4c9f74cee6e1f242f6f47e1c71b3c242a79084ea7fbbdcaf8b561"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 3985224192

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1080969973

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230606"
previous_tag = "2023-06-06"
previous_file = "ubuntu-lxqt_amd64_2023-06-06_00-27-rootfs.tar.zst"
previous_sha256 = "0ebcedc025efdc0f5678bb6ef264615dde0cabf2632925fb13f20c65db30b7a6"

current_version = "latest02"
current_date = "20230620"
old_file = "ubuntu-lxqt_amd64_2023-05-30_00-28-rootfs.tar.zst"
old_sha256 = "861bb78df468e8315bf98c33e4ca2473697d5ae98cb327a195d523dc37e0e80e"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-lxqt_amd64_2023-06-20_00-29-rootfs.tar.zst
# SHA256SUM=b41d831063b4c9f74cee6e1f242f6f47e1c71b3c242a79084ea7fbbdcaf8b561
# BUILD_DATE=20230620
# BUILD_TAG=2023-06-20
# STATUS=completed
# VERSION=latest02
# END_TIME=00:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-20
begin = 2023-06-20 00:03:09.296057584+00:00
start-sync_0 = 00:10:09
start-zstd = 00:13:27
start-sync_1 = 00:27:58
end-sync_1 = 00:29:00
end = 2023-06-20 00:29:00.452263180+00:00

[server]
repo = "cake233/ubuntu-lxqt-amd64"

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
