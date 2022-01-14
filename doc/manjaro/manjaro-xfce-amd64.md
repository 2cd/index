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

## manjaro-xfce-amd64.toml

```toml
[main]
name = "manjaro"
tag = ["xfce", "2022-01-14"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "manjaro-xfce_amd64_2022-01-14_12-40.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "f562253bdfbce9be20691df6b5ece35bd42f8970616af1e29f6cdfde446efe19"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3923977216

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1159010802

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220107"
previous_tag = "2022-01-07"
previous_file = "manjaro-xfce_amd64_2022-01-07_12-40-rootfs.tar.zst"
previous_sha256 = "13961bf068b6c30e6adb76faab66d3fa150f1356307d3a9641c9cbdc7b22e6f7"

current_version = "latest02"
current_date = "20220114"
old_file = "manjaro-xfce_amd64_2021-12-31_12-40-rootfs.tar.zst"
old_sha256 = "0f3bfd5de8d897993a917e91ad83d2c1d15ba6b645b8d70dce77766cafbcaac1"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-xfce_amd64_2022-01-14_12-40-rootfs.tar.zst
# SHA256SUM=f562253bdfbce9be20691df6b5ece35bd42f8970616af1e29f6cdfde446efe19
# BUILD_DATE=20220114
# BUILD_TAG=2022-01-14
# STATUS=completed
# VERSION=latest02
# END_TIME=12:40

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-14
begin = 2022-01-14 12:15:20.596086166+00:00
start-sync_0 = 12:24:45
start-zstd = 12:28:10
start-sync_1 = 12:39:13
end-sync_1 = 12:40:25
end = 2022-01-14 12:40:25.739519399+00:00

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
ldd = 'ldd (GNU libc) 2.33'
zsh = 'zsh 5.8 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
