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
tag = ["mate", "2023-03-14"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_arm64_2023-03-14_14-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "921c7d15b344bdd5769346949f55ebac4d197c2bfbff0d7e2305f10fb278523e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.6G"
tar_bytes = 2778450432

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "561M"
zstd_bytes = 587471258

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230307"
previous_tag = "2023-03-07"
previous_file = "fedora-mate_arm64_2023-03-07_16-03-rootfs.tar.zst"
previous_sha256 = "94926c6d7f602b8a30a0ac1dd97051b52e0500fe31cca987d1763c6a8fb629c6"

current_version = "latest02"
current_date = "20230314"
old_file = "fedora-mate_arm64_2023-02-28_17-33-rootfs.tar.zst"
old_sha256 = "3a724c3220be517e0e0fb4da2421e4a86c0fa5f8da5be698815128d44c17a2d8"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-mate_arm64_2023-03-14_14-29-rootfs.tar.zst
# SHA256SUM=921c7d15b344bdd5769346949f55ebac4d197c2bfbff0d7e2305f10fb278523e
# BUILD_DATE=20230314
# BUILD_TAG=2023-03-14
# STATUS=completed
# VERSION=latest02
# END_TIME=14:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-14
begin = 2023-03-14 13:02:41.764853356+00:00
start-sync_0 = 14:19:46
start-zstd = 14:21:07
start-sync_1 = 14:29:00
end-sync_1 = 14:29:36
end = 2023-03-14 14:29:36.164724249+00:00

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
ldd = 'ldd (GNU libc) 2.37.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
