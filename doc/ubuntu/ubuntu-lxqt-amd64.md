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
tag = ["lxqt", "2022-04-04", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "ubuntu-lxqt_amd64_2022-04-04_23-49.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "690d801707dc90586c09327feaebc255d87597c2642e9842d73f476be4d179cf"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 3976694784

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1009M"
zstd_bytes = 1057948892

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220328"
previous_tag = "2022-03-28"
previous_file = "ubuntu-lxqt_amd64_2022-03-28_23-45-rootfs.tar.zst"
previous_sha256 = "2b04a86f6a6924213bb490cbdbefe1d7d09a3b1ab25cf7e7ca4218ab2efaf776"

current_version = "latest02"
current_date = "20220404"
old_file = "ubuntu-lxqt_amd64_2022-03-24_19-09-rootfs.tar.zst"
old_sha256 = "d50388630273b5aff86bb409aa8f3c455d267319f3bd37ddef5e1a7074776568"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-lxqt_amd64_2022-04-04_23-49-rootfs.tar.zst
# SHA256SUM=690d801707dc90586c09327feaebc255d87597c2642e9842d73f476be4d179cf
# BUILD_DATE=20220404
# BUILD_TAG=2022-04-04
# STATUS=completed
# VERSION=latest02
# END_TIME=23:49

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-04
begin = 2022-04-04 23:21:35.982458004+00:00
start-sync_0 = 23:28:34
start-zstd = 23:32:50
start-sync_1 = 23:47:56
end-sync_1 = 23:49:06
end = 2022-04-04 23:49:06.542406029+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.8.1 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
