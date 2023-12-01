# manjaro-xfce-amd64

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
    --name manjaro-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/manjaro-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it manjaro-xfce-amd64 zsh
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

## manjaro-xfce-amd64.toml

```toml
[main]
name = "manjaro"
tag = ["xfce", "2023-12-01"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_amd64_2023-12-01_12-36.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c5c5d8fc4325a891412c9cd57d3927b6b9e4716add52ef4135d91c6f122fab00"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.9G"
tar_bytes = 4135536128

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1204378929

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231124"
previous_tag = "2023-11-24"
previous_file = "manjaro-xfce_amd64_2023-11-24_12-35-rootfs.tar.zst"
previous_sha256 = "563d4d005b763ee8aff43bc1c95eb79caaa0324d4d3f81832494ae863e9137a6"

current_version = "latest01"
current_date = "20231201"
old_file = "manjaro-xfce_amd64_2023-11-17_12-39-rootfs.tar.zst"
old_sha256 = "5f8e7483b18f74f1444e3445ac02960f94690fff7d87ef15a63452c159da3528"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-xfce_amd64_2023-12-01_12-36-rootfs.tar.zst
# SHA256SUM=c5c5d8fc4325a891412c9cd57d3927b6b9e4716add52ef4135d91c6f122fab00
# BUILD_DATE=20231201
# BUILD_TAG=2023-12-01
# STATUS=completed
# VERSION=latest01
# END_TIME=12:36

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-01
begin = 2023-12-01 12:17:27.713949928+00:00
start-sync_0 = 12:21:40
start-zstd = 12:23:44
start-sync_1 = 12:35:56
end-sync_1 = 12:36:48
end = 2023-12-01 12:36:48.489717997+00:00

[server]
repo = "cake233/manjaro-xfce-amd64"

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
ldd = 'ldd (GNU libc) 2.38'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
