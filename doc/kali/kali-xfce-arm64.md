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

```sh
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
tag = ["xfce", "2021-12-30"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "kali-xfce_arm64_2021-12-30_13-41.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "5fff99a178dc4a24264f61c0c6f1aa4f40003768845c812c3cf6c433f2d606a7"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.5G"
tar_bytes = 5904987136

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1671804879

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211223"
previous_tag = "2021-12-23"
previous_file = "kali-xfce_arm64_2021-12-23_13-49-rootfs.tar.zst"
previous_sha256 = "470c4a53b1dc8751587c4881ccf7003bd0531e59a8709a0dcea2eb0923232b95"

current_version = "latest01"
current_date = "20211230"
old_file = "kali-xfce_arm64_2021-12-16_13-42-rootfs.tar.zst"
old_sha256 = "de0cf79a4a39dd3f0458fef1f99f8b6d4fb7ad4b3bf229aab276a75d031db26a"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2021-12-30_13-41-rootfs.tar.zst
# SHA256SUM=5fff99a178dc4a24264f61c0c6f1aa4f40003768845c812c3cf6c433f2d606a7
# BUILD_DATE=20211230
# BUILD_TAG=2021-12-30
# STATUS=completed
# VERSION=latest01
# END_TIME=13:41

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-30
begin = 2021-12-30 12:18:19.072515221+00:00
start-sync_0 = 13:18:51
start-zstd = 13:24:46
start-sync_1 = 13:39:56
end-sync_1 = 13:41:36
end = 2021-12-30 13:41:36.858307421+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (Debian GLIBC 2.33-1) 2.33'
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
