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
tag = ["xfce", "2022-07-20"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_arm64_2022-07-20_13-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d25672943b94f3c2043ed85f71bee98e51a1927faf4b0b6678a5626626654350"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4264607232

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1216601099

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220713"
previous_tag = "2022-07-13"
previous_file = "debian-xfce_arm64_2022-07-13_13-14-rootfs.tar.zst"
previous_sha256 = "42185f0dc770038870242afa7ad1fbf8140273f85caabc75a3402597485abbce"

current_version = "latest01"
current_date = "20220720"
old_file = "debian-xfce_arm64_2022-07-06_13-12-rootfs.tar.zst"
old_sha256 = "d7aa56c7497e9e5c46308d374d3727675f312bb5af26b752644002daf15ab184"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-xfce_arm64_2022-07-20_13-14-rootfs.tar.zst
# SHA256SUM=d25672943b94f3c2043ed85f71bee98e51a1927faf4b0b6678a5626626654350
# BUILD_DATE=20220720
# BUILD_TAG=2022-07-20
# STATUS=completed
# VERSION=latest01
# END_TIME=13:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-20
begin = 2022-07-20 12:22:51.075990328+00:00
start-sync_0 = 12:55:37
start-zstd = 12:59:18
start-sync_1 = 13:13:28
end-sync_1 = 13:14:38
end = 2022-07-20 13:14:38.727423017+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-8) 2.33'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
