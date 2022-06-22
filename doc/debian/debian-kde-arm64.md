# debian-kde-arm64

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
    --name debian-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-kde-arm64 zsh
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

## debian-kde-arm64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2022-06-22"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_arm64_2022-06-22_13-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8207f85f8700520a4f2bb4ed911e5c5564c5caffa8d99aa16cb21d0d2a4c07ad"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.3G"
tar_bytes = 5626234880

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1634127961

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220615"
previous_tag = "2022-06-15"
previous_file = "debian-kde_arm64_2022-06-15_13-30-rootfs.tar.zst"
previous_sha256 = "f5ebe770d5970e89ca5e43471ec855fbd2f61f9036a7e28ca4dbc99139911cd4"

current_version = "latest01"
current_date = "20220622"
old_file = "debian-kde_arm64_2022-06-08_13-29-rootfs.tar.zst"
old_sha256 = "a7b605b59f0884d4d2192922a5100ef213ebbe26f2d5ee25a10aadad99c8da34"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2022-06-22_13-29-rootfs.tar.zst
# SHA256SUM=8207f85f8700520a4f2bb4ed911e5c5564c5caffa8d99aa16cb21d0d2a4c07ad
# BUILD_DATE=20220622
# BUILD_TAG=2022-06-22
# STATUS=completed
# VERSION=latest01
# END_TIME=13:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-22
begin = 2022-06-22 12:23:40.231521805+00:00
start-sync_0 = 13:03:05
start-zstd = 13:07:43
start-sync_1 = 13:27:46
end-sync_1 = 13:29:20
end = 2022-06-22 13:29:20.890698534+00:00

[server]
repo = "cake233/debian-kde-arm64"

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
