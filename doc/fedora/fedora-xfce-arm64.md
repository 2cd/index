# fedora-xfce-arm64

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
    --name fedora-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-xfce-arm64 zsh
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

## fedora-xfce-arm64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2023-08-15"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_arm64_2023-08-15_12-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2bb8f2687fab241c5edb7cdcaa5a3ad53ba940bddcbdfae63ca857a4cc09a88a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.2G"
tar_bytes = 3368198656

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "744M"
zstd_bytes = 779654027

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230808"
previous_tag = "2023-08-08"
previous_file = "fedora-xfce_arm64_2023-08-08_13-44-rootfs.tar.zst"
previous_sha256 = "a609255500cf0afc5d9cce5b5fe0d6cc099faa4094f1bcb6c611950c2001fe97"

current_version = "latest02"
current_date = "20230815"
old_file = "fedora-xfce_arm64_2023-08-01_13-29-rootfs.tar.zst"
old_sha256 = "9acb44f150543268137c506ec85d3d60fec95390618862e0e8582805be8b7f7b"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-xfce_arm64_2023-08-15_12-59-rootfs.tar.zst
# SHA256SUM=2bb8f2687fab241c5edb7cdcaa5a3ad53ba940bddcbdfae63ca857a4cc09a88a
# BUILD_DATE=20230815
# BUILD_TAG=2023-08-15
# STATUS=completed
# VERSION=latest02
# END_TIME=12:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-15
begin = 2023-08-15 12:15:17.849865402+00:00
start-sync_0 = 12:46:27
start-zstd = 12:48:11
start-sync_1 = 12:58:40
end-sync_1 = 12:59:39
end = 2023-08-15 12:59:39.990264653+00:00

[server]
repo = "cake233/fedora-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.38'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
