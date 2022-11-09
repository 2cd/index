# debian-xfce-arm64

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
    --name debian-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-xfce-arm64 zsh
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

## debian-xfce-arm64.toml

```toml
[main]
name = "debian"
tag = ["xfce", "2022-11-09"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_arm64_2022-11-09_13-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "86be9c10c583935af063877263a6db29873acd43f34d7c3602372c16c53f57b7"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4398397440

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1231343715

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221102"
previous_tag = "2022-11-02"
previous_file = "debian-xfce_arm64_2022-11-02_13-34-rootfs.tar.zst"
previous_sha256 = "c6d000bed4de8b45369e30eac9d4a36b6bd3b6d08c83824195d810ebc0004c0b"

current_version = "latest02"
current_date = "20221109"
old_file = "debian-xfce_arm64_2022-10-26_13-11-rootfs.tar.zst"
old_sha256 = "bb5055289afe22e16117283141abb0eac668a9a40ecb0d5e5ff0bc77120de725"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-xfce_arm64_2022-11-09_13-09-rootfs.tar.zst
# SHA256SUM=86be9c10c583935af063877263a6db29873acd43f34d7c3602372c16c53f57b7
# BUILD_DATE=20221109
# BUILD_TAG=2022-11-09
# STATUS=completed
# VERSION=latest02
# END_TIME=13:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-09
begin = 2022-11-09 12:18:52.503815170+00:00
start-sync_0 = 12:51:12
start-zstd = 12:54:36
start-sync_1 = 13:08:42
end-sync_1 = 13:09:51
end = 2022-11-09 13:09:51.856461030+00:00

[server]
repo = "cake233/debian-xfce-arm64"

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
ldd = 'ldd (Debian GLIBC 2.36-4) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
