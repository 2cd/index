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
tag = ["mate", "2023-07-04", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-mate_arm64_2023-07-04_01-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5b5b05db88a687e41265ab37def0876e7feebf1c72f19e9d335b2207aabc54e5"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.3G"
tar_bytes = 4575143424

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1230472800

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230627"
previous_tag = "2023-06-27"
previous_file = "ubuntu-mate_arm64_2023-06-27_00-56-rootfs.tar.zst"
previous_sha256 = "df18b360734b0588f88c726afad6f61574b5f1093b773ece16644bc491f9a2d8"

current_version = "latest01"
current_date = "20230704"
old_file = "ubuntu-mate_arm64_2023-06-20_01-07-rootfs.tar.zst"
old_sha256 = "74c73ad833712a24e4e4983280e616bffbb0cf93ad77af44711e17bd0bb467a6"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-mate_arm64_2023-07-04_01-05-rootfs.tar.zst
# SHA256SUM=5b5b05db88a687e41265ab37def0876e7feebf1c72f19e9d335b2207aabc54e5
# BUILD_DATE=20230704
# BUILD_TAG=2023-07-04
# STATUS=completed
# VERSION=latest01
# END_TIME=01:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-04
begin = 2023-07-04 00:03:17.687817939+00:00
start-sync_0 = 00:41:35
start-zstd = 00:46:03
start-sync_1 = 01:04:25
end-sync_1 = 01:05:55
end = 2023-07-04 01:05:55.221002821+00:00

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
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
