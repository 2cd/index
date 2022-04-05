# fedora-mate-arm64

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
    --name fedora-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-arm64 zsh
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

## fedora-mate-arm64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2022-04-05"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "fedora-mate_arm64_2022-04-05_12-40.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "109c658fcd6c204a2230c92d5d5c270cee763cb9eb041ba4c77800cebaba2b2d"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.6G"
tar_bytes = 2721397248

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "672M"
zstd_bytes = 703783201

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220329"
previous_tag = "2022-03-29"
previous_file = "fedora-mate_arm64_2022-03-29_12-55-rootfs.tar.zst"
previous_sha256 = "c89668f13ce76c4f6f3fe8b6f94ea9146cb2ecb3149e2f0b7cf84468885a79ab"

current_version = "latest02"
current_date = "20220405"
old_file = "fedora-mate_arm64_2022-03-22_13-44-rootfs.tar.zst"
old_sha256 = "306e8e4da76735b3edb45c9da46d6cde0922e2a9e7f0965e7ba35b5559b54eec"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-mate_arm64_2022-04-05_12-40-rootfs.tar.zst
# SHA256SUM=109c658fcd6c204a2230c92d5d5c270cee763cb9eb041ba4c77800cebaba2b2d
# BUILD_DATE=20220405
# BUILD_TAG=2022-04-05
# STATUS=completed
# VERSION=latest02
# END_TIME=12:40

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-05
begin = 2022-04-05 11:38:08.983702131+00:00
start-sync_0 = 12:30:30
start-zstd = 12:32:10
start-sync_1 = 12:40:06
end-sync_1 = 12:40:53
end = 2022-04-05 12:40:53.384543646+00:00

[server]
repo = "cake233/fedora-mate-arm64"

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.8.1 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
