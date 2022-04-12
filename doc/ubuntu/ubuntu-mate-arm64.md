# ubuntu-mate-arm64

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
    --name ubuntu-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-mate-arm64 zsh
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

## ubuntu-mate-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["mate", "2022-04-11", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true
syntax_version = "0.0.0-alpha.3"

[file]
name = "ubuntu-mate_arm64_2022-04-12_00-15.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "86bda764fa2e7c4af5b6baec5b4746fcb1bc51e41dc04cdd878f9514ae356d5e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4325635584

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1139933369

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220405"
previous_tag = "2022-04-04"
previous_file = "ubuntu-mate_arm64_2022-04-05_00-17-rootfs.tar.zst"
previous_sha256 = "c4044a699fab4758cc1914f76d4c40c97a66d22734d489a40f1a262ff7e7d03f"

current_version = "latest01"
current_date = "20220412"
old_file = "ubuntu-mate_arm64_2022-03-29_00-11-rootfs.tar.zst"
old_sha256 = "a316ff6816764118c9a0f85fd9d5e60846b16bed4be5163c7f79ad34ec535a5d"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-mate_arm64_2022-04-12_00-15-rootfs.tar.zst
# SHA256SUM=86bda764fa2e7c4af5b6baec5b4746fcb1bc51e41dc04cdd878f9514ae356d5e
# BUILD_DATE=20220412
# BUILD_TAG=2022-04-11
# STATUS=completed
# VERSION=latest01
# END_TIME=00:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-11
begin = 2022-04-11 23:17:43.807519467+00:00
start-sync_0 = 23:53:12
start-zstd = 23:57:25
start-sync_1 = 00:14:04
end-sync_1 = 00:15:16
end = 2022-04-12 00:15:16.601814335+00:00

[server]
repo = "cake233/ubuntu-mate-arm64"

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
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
