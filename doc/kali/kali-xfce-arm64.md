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
tag = ["xfce", "2023-10-12"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_arm64_2023-10-12_14-43.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "df63a9e416c2f16fb07d364cc7ff9f00edb942fb7d72258a3b7979e0812637b6"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.0G"
tar_bytes = 5337934336

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1450766652

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231005"
previous_tag = "2023-10-05"
previous_file = "kali-xfce_arm64_2023-10-05_14-26-rootfs.tar.zst"
previous_sha256 = "5943813fed7bf8c95fdacd26d572c6026f1010224bf51859a5c6f690ddb05053"

current_version = "latest01"
current_date = "20231012"
old_file = "kali-xfce_arm64_2023-09-28_13-43-rootfs.tar.zst"
old_sha256 = "0adf1fdecbbc9650ff2aee01c0b49b8143361a7e661205c3921c7902c606d6a8"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2023-10-12_14-43-rootfs.tar.zst
# SHA256SUM=df63a9e416c2f16fb07d364cc7ff9f00edb942fb7d72258a3b7979e0812637b6
# BUILD_DATE=20231012
# BUILD_TAG=2023-10-12
# STATUS=completed
# VERSION=latest01
# END_TIME=14:43

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-12
begin = 2023-10-12 12:37:09.370990104+00:00
start-sync_0 = 14:18:12
start-zstd = 14:22:40
start-sync_1 = 14:40:45
end-sync_1 = 14:43:02
end = 2023-10-12 14:43:02.551729492+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
