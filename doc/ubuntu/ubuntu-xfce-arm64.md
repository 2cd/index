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
tag = ["xfce", "2024-02-20", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_arm64_2024-02-20_02-48.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d798001516b3933bb7e783284c536ca8bbaff898c33bd234684faf3677b17057"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.7G"
tar_bytes = 5036152320

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1294406813

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231128"
previous_tag = "2023-11-28"
previous_file = "ubuntu-xfce_arm64_2023-11-28_01-23-rootfs.tar.zst"
previous_sha256 = "aa3f7ce4ef07c338f6cf4a3e213f476c8dff613bfd77105eafae8a04e3475d4a"

current_version = "latest02"
current_date = "20240220"
old_file = "ubuntu-xfce_arm64_2023-11-21_01-20-rootfs.tar.zst"
old_sha256 = "8f0978224c5836e9b566878cde09920a16c85e7564da6f8b7e0239eba0edc7e8"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-xfce_arm64_2024-02-20_02-48-rootfs.tar.zst
# SHA256SUM=d798001516b3933bb7e783284c536ca8bbaff898c33bd234684faf3677b17057
# BUILD_DATE=20240220
# BUILD_TAG=2024-02-20
# STATUS=completed
# VERSION=latest02
# END_TIME=02:48

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-20
begin = 2024-02-20 00:43:03.040583542+00:00
start-sync_0 = 02:32:13
start-zstd = 02:34:45
start-sync_1 = 02:47:29
end-sync_1 = 02:48:28
end = 2024-02-20 02:48:28.263343483+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.38-3ubuntu1) 2.38'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
