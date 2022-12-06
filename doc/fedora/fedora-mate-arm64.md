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
tag = ["mate", "2022-12-06"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_arm64_2022-12-06_14-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3c4f66f8b3275c46458fb2a2c2eaf162627591bdfd25e9894aac9f5d33318c0b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.7G"
tar_bytes = 7098503680

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.8G"
zstd_bytes = 1851638505

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221129"
previous_tag = "2022-11-29"
previous_file = "fedora-mate_arm64_2022-11-29_14-28-rootfs.tar.zst"
previous_sha256 = "4e5a1492999a8d4b928306a99979af43cb26d9520b64ab57fa64c08f40741ca9"

current_version = "latest02"
current_date = "20221206"
old_file = "fedora-mate_arm64_2022-11-22_14-36-rootfs.tar.zst"
old_sha256 = "5b644ac6c72114f0383a2553af7f6000139920a5fa62911366118fa27cc8b777"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-mate_arm64_2022-12-06_14-29-rootfs.tar.zst
# SHA256SUM=3c4f66f8b3275c46458fb2a2c2eaf162627591bdfd25e9894aac9f5d33318c0b
# BUILD_DATE=20221206
# BUILD_TAG=2022-12-06
# STATUS=completed
# VERSION=latest02
# END_TIME=14:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-06
begin = 2022-12-06 12:43:13.609314100+00:00
start-sync_0 = 13:59:46
start-zstd = 14:05:10
start-sync_1 = 14:27:52
end-sync_1 = 14:29:37
end = 2022-12-06 14:29:37.486079212+00:00

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
