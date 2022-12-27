# ubuntu-xfce-arm64

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
    --name ubuntu-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-xfce-arm64 zsh
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

## ubuntu-xfce-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2022-12-27", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_arm64_2022-12-27_01-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8692a9da10854fc5b9d25dcc5b96e47940fd184b90c218b7624a3eff6fb3e270"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3888437248

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1010M"
zstd_bytes = 1058354658

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221220"
previous_tag = "2022-12-20"
previous_file = "ubuntu-xfce_arm64_2022-12-20_02-45-rootfs.tar.zst"
previous_sha256 = "d793ce2232299a918595bfb83042f887a6880bd4be8af0753bf5e90695c82e60"

current_version = "latest01"
current_date = "20221227"
old_file = "ubuntu-xfce_arm64_2022-12-13_00-50-rootfs.tar.zst"
old_sha256 = "81683c4e8a0ba75564f1e08b5f8d3828c14d84cced6fdbc60bdcbe87053924fe"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-xfce_arm64_2022-12-27_01-08-rootfs.tar.zst
# SHA256SUM=8692a9da10854fc5b9d25dcc5b96e47940fd184b90c218b7624a3eff6fb3e270
# BUILD_DATE=20221227
# BUILD_TAG=2022-12-27
# STATUS=completed
# VERSION=latest01
# END_TIME=01:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-27
begin = 2022-12-27 00:02:58.258872690+00:00
start-sync_0 = 00:45:48
start-zstd = 00:49:23
start-sync_1 = 01:07:11
end-sync_1 = 01:08:22
end = 2022-12-27 01:08:22.237684319+00:00

[server]
repo = "cake233/ubuntu-xfce-arm64"

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
