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

```sh
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
tag = ["xfce", "2022-01-25", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "ubuntu-xfce_amd64_2022-01-25_00-37.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "d2205e986642bfc967bd710483435e1fa7b5117a2e5dd66d7c7aa5bffc38e359"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.8G"
tar_bytes = 2975447040

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "768M"
zstd_bytes = 804785023

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220125"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-xfce_amd64_2022-01-25_00-37-rootfs.tar.zst
# SHA256SUM=d2205e986642bfc967bd710483435e1fa7b5117a2e5dd66d7c7aa5bffc38e359
# BUILD_DATE=20220125
# BUILD_TAG=2022-01-25
# STATUS=completed
# VERSION=latest01
# END_TIME=00:37

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-25
begin = 2022-01-25 00:21:02.833619529+00:00
start-sync_0 = 00:27:00
start-zstd = 00:29:22
start-sync_1 = 00:36:43
end-sync_1 = 00:37:33
end = 2022-01-25 00:37:33.597299587+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.34-0ubuntu3) 2.34'
zsh = 'zsh 5.8 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
