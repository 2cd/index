# ubuntu-xfce-amd64

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
    --name ubuntu-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-xfce-amd64 zsh
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

## ubuntu-xfce-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2022-08-16", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_amd64_2022-08-16_00-52.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b8c67f64515ad38b0641b1ef9d66a116b4bacafbd9eb3ebfddd4e4fbce79dfb9"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.3G"
tar_bytes = 3538812416

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "922M"
zstd_bytes = 966034111

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220809"
previous_tag = "2022-08-09"
previous_file = "ubuntu-xfce_amd64_2022-08-09_00-45-rootfs.tar.zst"
previous_sha256 = "138387fc530f18a8d4b52461b47a32fe0bcff944fe5de60810142f8db4a78859"

current_version = "latest01"
current_date = "20220816"
old_file = "ubuntu-xfce_amd64_2022-07-12_00-45-rootfs.tar.zst"
old_sha256 = "71c3ba5587e1fa534f98bd95ea43cb224c06c0848fa1c3433df02c96a6b7f8be"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-xfce_amd64_2022-08-16_00-52-rootfs.tar.zst
# SHA256SUM=b8c67f64515ad38b0641b1ef9d66a116b4bacafbd9eb3ebfddd4e4fbce79dfb9
# BUILD_DATE=20220816
# BUILD_TAG=2022-08-16
# STATUS=completed
# VERSION=latest01
# END_TIME=00:52

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-16
begin = 2022-08-16 00:24:39.360138679+00:00
start-sync_0 = 00:31:36
start-zstd = 00:35:16
start-sync_1 = 00:51:04
end-sync_1 = 00:52:16
end = 2022-08-16 00:52:16.554067640+00:00

[server]
repo = "cake233/ubuntu-xfce-amd64"

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
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
