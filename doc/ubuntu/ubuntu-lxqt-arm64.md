# ubuntu-lxqt-arm64

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
    --name ubuntu-lxqt-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-lxqt-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-lxqt-arm64 zsh
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

## ubuntu-lxqt-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2023-08-22", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_arm64_2023-08-22_01-23.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4d0bbf58654e915b61c5acc6e040556d8e9186db2069936e2003d014e6948400"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.9G"
tar_bytes = 5204490752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1398955432

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230816"
previous_tag = "2023-08-16"
previous_file = "ubuntu-lxqt_arm64_2023-08-16_15-41-rootfs.tar.zst"
previous_sha256 = "cb5e541c59cf6ea01fa4d4e8752a7b6d52d314179d34053a2c57480d6327f076"

current_version = "latest02"
current_date = "20230822"
old_file = "ubuntu-lxqt_arm64_2023-08-15_01-00-rootfs.tar.zst"
old_sha256 = "21246354e69d8e6d48248949d13418a5d3d31416648e10f7bf28db83267463a8"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-lxqt_arm64_2023-08-22_01-23-rootfs.tar.zst
# SHA256SUM=4d0bbf58654e915b61c5acc6e040556d8e9186db2069936e2003d014e6948400
# BUILD_DATE=20230822
# BUILD_TAG=2023-08-22
# STATUS=completed
# VERSION=latest02
# END_TIME=01:23

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-22
begin = 2023-08-22 00:24:08.687037941+00:00
start-sync_0 = 00:58:38
start-zstd = 01:03:08
start-sync_1 = 01:21:59
end-sync_1 = 01:23:42
end = 2023-08-22 01:23:42.296509026+00:00

[server]
repo = "cake233/ubuntu-lxqt-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.37-0ubuntu2) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
