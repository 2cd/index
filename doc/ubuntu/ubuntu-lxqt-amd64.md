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
tag = ["lxqt", "2022-10-25", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_amd64_2022-10-25_00-47.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d3e9a1660f2d1ff8f2f4c3836c85d0d2c9cb1e7b1e7e58bc604621ab0d83aea5"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3949490688

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1016M"
zstd_bytes = 1065177925

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221018"
previous_tag = "2022-10-18"
previous_file = "ubuntu-lxqt_amd64_2022-10-18_00-56-rootfs.tar.zst"
previous_sha256 = "773fc4046a57ababe26ff364c976a180fd3ccfa6df92d59b3f148ca65ea61d17"

current_version = "latest01"
current_date = "20221025"
old_file = "ubuntu-lxqt_amd64_2022-10-11_00-48-rootfs.tar.zst"
old_sha256 = "984929237b9251b6b8820f5244164f783dce73cf4df8ff52f2d177f372766f11"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-lxqt_amd64_2022-10-25_00-47-rootfs.tar.zst
# SHA256SUM=d3e9a1660f2d1ff8f2f4c3836c85d0d2c9cb1e7b1e7e58bc604621ab0d83aea5
# BUILD_DATE=20221025
# BUILD_TAG=2022-10-25
# STATUS=completed
# VERSION=latest01
# END_TIME=00:47

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-25
begin = 2022-10-25 00:23:00.931304227+00:00
start-sync_0 = 00:28:46
start-zstd = 00:31:54
start-sync_1 = 00:46:04
end-sync_1 = 00:47:08
end = 2022-10-25 00:47:08.876128734+00:00

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
