# ubuntu-kde-arm64

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
    --name ubuntu-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-arm64 zsh
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

## ubuntu-kde-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2022-07-26", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_arm64_2022-07-26_01-24.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a420822c6b7002bdd1395b251bbe6993e011e6266607667f9e74f25d25871a94"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4930451456

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1366155727

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220712"
previous_tag = "2022-07-12"
previous_file = "ubuntu-kde_arm64_2022-07-12_01-18-rootfs.tar.zst"
previous_sha256 = "f6d0a2fed8dfad66d489417d8f784781188865ce354048ad9ee5c8119ba8ea8a"

current_version = "latest02"
current_date = "20220726"
old_file = "ubuntu-kde_arm64_2022-07-05_01-12-rootfs.tar.zst"
old_sha256 = "ff76c6d73170e36a4b881abbecba827212eaed625dcc8fdd074a835cf5db0f4c"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-kde_arm64_2022-07-26_01-24-rootfs.tar.zst
# SHA256SUM=a420822c6b7002bdd1395b251bbe6993e011e6266607667f9e74f25d25871a94
# BUILD_DATE=20220726
# BUILD_TAG=2022-07-26
# STATUS=completed
# VERSION=latest02
# END_TIME=01:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-26
begin = 2022-07-26 00:23:58.704445462+00:00
start-sync_0 = 01:01:15
start-zstd = 01:05:51
start-sync_1 = 01:22:47
end-sync_1 = 01:24:09
end = 2022-07-26 01:24:09.133329778+00:00

[server]
repo = "cake233/ubuntu-kde-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
