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
tag = ["xfce", "2022-07-26", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_amd64_2022-07-26_00-47.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f5075606025742aae53861d9fec9238417acc6eeb23ec0bd846c4fe1ba68bc06"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.4G"
tar_bytes = 3547295744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "919M"
zstd_bytes = 963175246

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220712"
previous_tag = "2022-07-12"
previous_file = "ubuntu-xfce_amd64_2022-07-12_00-45-rootfs.tar.zst"
previous_sha256 = "71c3ba5587e1fa534f98bd95ea43cb224c06c0848fa1c3433df02c96a6b7f8be"

current_version = "latest02"
current_date = "20220726"
old_file = "ubuntu-xfce_amd64_2022-07-05_00-38-rootfs.tar.zst"
old_sha256 = "62a3bf2d4155170e8149e40b6631748b6fc438f90ab91c55aec2f338d5e656d2"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-xfce_amd64_2022-07-26_00-47-rootfs.tar.zst
# SHA256SUM=f5075606025742aae53861d9fec9238417acc6eeb23ec0bd846c4fe1ba68bc06
# BUILD_DATE=20220726
# BUILD_TAG=2022-07-26
# STATUS=completed
# VERSION=latest02
# END_TIME=00:47

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-26
begin = 2022-07-26 00:23:58.449196660+00:00
start-sync_0 = 00:30:07
start-zstd = 00:33:14
start-sync_1 = 00:46:23
end-sync_1 = 00:47:22
end = 2022-07-26 00:47:22.877405065+00:00

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
