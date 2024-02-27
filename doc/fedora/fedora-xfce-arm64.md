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
tag = ["xfce", "2024-02-27"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_arm64_2024-02-27_13-50.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f50170ff6a1dc72dcdb5d3f0d4cdce43ade726d26de465db97c9cbdbb376b59e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.1G"
tar_bytes = 6547804672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1695252007

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231121"
previous_tag = "2023-11-21"
previous_file = "fedora-xfce_arm64_2023-11-21_14-00-rootfs.tar.zst"
previous_sha256 = "717385e3d0ea1b98c5bcdd97faa336f3957455864ba6d5ed2ec961e6641110d1"

current_version = "latest01"
current_date = "20240227"
old_file = "fedora-xfce_arm64_2023-11-14_14-19-rootfs.tar.zst"
old_sha256 = "a4504b6ac71d7f538e9f6af20d1801586355fb2b345ffb8f54a196c0c4d0d81d"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-xfce_arm64_2024-02-27_13-50-rootfs.tar.zst
# SHA256SUM=f50170ff6a1dc72dcdb5d3f0d4cdce43ade726d26de465db97c9cbdbb376b59e
# BUILD_DATE=20240227
# BUILD_TAG=2024-02-27
# STATUS=completed
# VERSION=latest01
# END_TIME=13:50

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-27
begin = 2024-02-27 12:28:39.756400495+00:00
start-sync_0 = 13:31:36
start-zstd = 13:34:52
start-sync_1 = 13:49:16
end-sync_1 = 13:50:30
end = 2024-02-27 13:50:30.059975037+00:00

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
ldd = 'ldd (GNU libc) 2.39.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
