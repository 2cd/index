# kali-xfce-arm64

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
    --name kali-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-arm64 zsh
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

## kali-xfce-arm64.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2022-09-01"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_arm64_2022-09-01_13-40.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "eeb05cb30d23acd93db9f6e026eee62265fa397affdb4bbf1b12f6ae00357074"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.0G"
tar_bytes = 6350379520

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1713058906

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220825"
previous_tag = "2022-08-25"
previous_file = "kali-xfce_arm64_2022-08-25_13-42-rootfs.tar.zst"
previous_sha256 = "026ab92d97edc89e9c8bc47afe97584c2d44f47f3e760771b25959cabcb2059e"

current_version = "latest02"
current_date = "20220901"
old_file = "kali-xfce_arm64_2022-08-18_13-41-rootfs.tar.zst"
old_sha256 = "1d8c468cd7ba8ccd1c355d952b55966ef59cf1e81a4f32afcb9c594ecdff9cc0"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2022-09-01_13-40-rootfs.tar.zst
# SHA256SUM=eeb05cb30d23acd93db9f6e026eee62265fa397affdb4bbf1b12f6ae00357074
# BUILD_DATE=20220901
# BUILD_TAG=2022-09-01
# STATUS=completed
# VERSION=latest02
# END_TIME=13:40

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-01
begin = 2022-09-01 12:18:08.930575466+00:00
start-sync_0 = 13:07:41
start-zstd = 13:14:01
start-sync_1 = 13:38:18
end-sync_1 = 13:40:04
end = 2022-09-01 13:40:04.132186323+00:00

[server]
repo = "cake233/kali-xfce-arm64"

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
ldd = 'ldd (Debian GLIBC 2.34-4) 2.34'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
