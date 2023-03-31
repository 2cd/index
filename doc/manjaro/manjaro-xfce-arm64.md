# manjaro-xfce-arm64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
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
    --name manjaro-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/manjaro-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it manjaro-xfce-arm64 zsh
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

## manjaro-xfce-arm64.toml

```toml
[main]
name = "manjaro"
tag = ["xfce", "2023-03-31"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_arm64_2023-03-31_13-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d994e0958b2a35f4bf429d8fda7c18a3b578509e70f15d380ac9302e575bb4d1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.2G"
tar_bytes = 4505757696

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1305783263

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230324"
previous_tag = "2023-03-24"
previous_file = "manjaro-xfce_arm64_2023-03-24_12-55-rootfs.tar.zst"
previous_sha256 = "30e1fdd35f5b3b1572a887dbe8dec748805715a151dad7d4475c3ab7df29bde3"

current_version = "latest01"
current_date = "20230331"
old_file = "manjaro-xfce_arm64_2023-03-17_12-54-rootfs.tar.zst"
old_sha256 = "c8aa5342401e6bb59bcfb6d000f57c84696f306e9e5b9ea02f43570fc50b8834"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-xfce_arm64_2023-03-31_13-08-rootfs.tar.zst
# SHA256SUM=d994e0958b2a35f4bf429d8fda7c18a3b578509e70f15d380ac9302e575bb4d1
# BUILD_DATE=20230331
# BUILD_TAG=2023-03-31
# STATUS=completed
# VERSION=latest01
# END_TIME=13:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-31
begin = 2023-03-31 12:25:49.820151262+00:00
start-sync_0 = 12:43:05
start-zstd = 12:47:20
start-sync_1 = 13:07:16
end-sync_1 = 13:08:40
end = 2023-03-31 13:08:40.098898174+00:00

[server]
repo = "cake233/manjaro-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
