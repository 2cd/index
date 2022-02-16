# arch-mate-arm64

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
    --name arch-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-mate-arm64 zsh
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

## arch-mate-arm64.toml

```toml
[main]
name = "arch"
tag = ["mate", "2022-02-16"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "arch-mate_arm64_2022-02-16_01-02.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "4847519a002d9279f77f45789845a52a005410c672b3ebc10453350d773ef8eb"

# zstd: [1-22]
zstd-level = 15

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.9G"
tar_bytes = 5202130432

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1572254127

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220209"
previous_tag = "2022-02-09"
previous_file = "arch-mate_arm64_2022-02-09_01-09-rootfs.tar.zst"
previous_sha256 = "9a8f98e65f4aec61472be5f2909a41ea4d84e6a23bfc0ef387933b263bb964a3"

current_version = "latest01"
current_date = "20220216"
old_file = "arch-mate_arm64_2022-02-02_01-03-rootfs.tar.zst"
old_sha256 = "c01db310964e26dca25cc11590999996d1908a0812167b3f841189b883b13064"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-mate_arm64_2022-02-16_01-02-rootfs.tar.zst
# SHA256SUM=4847519a002d9279f77f45789845a52a005410c672b3ebc10453350d773ef8eb
# BUILD_DATE=20220216
# BUILD_TAG=2022-02-16
# STATUS=completed
# VERSION=latest01
# END_TIME=01:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-16
begin = 2022-02-16 00:31:15.279578694+00:00
start-sync_0 = 00:48:35
start-zstd = 00:53:47
start-sync_1 = 01:00:35
end-sync_1 = 01:02:08
end = 2022-02-16 01:02:08.707511946+00:00

[server]
repo = "cake233/arch-mate-arm64"

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
ldd = 'ldd (GNU libc) 2.33'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
