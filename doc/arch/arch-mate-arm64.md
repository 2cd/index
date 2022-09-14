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

## arch-mate-arm64.toml

```toml
[main]
name = "arch"
tag = ["mate", "2022-09-14"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-mate_arm64_2022-09-14_01-15.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "174efdb0995849b1c0c880a6d21f7ffd18a23b246679c3fb9c9c10309a625a64"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.9G"
tar_bytes = 5180180992

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1437731853

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220907"
previous_tag = "2022-09-07"
previous_file = "arch-mate_arm64_2022-09-07_01-18-rootfs.tar.zst"
previous_sha256 = "adea3f2827e05c5cf9ac595e3b3099c87c76042af0cb21b63d20131c337c24f9"

current_version = "latest02"
current_date = "20220914"
old_file = "arch-mate_arm64_2022-08-31_01-38-rootfs.tar.zst"
old_sha256 = "d07c6406c1480e63f6c6f96510f1de438e3eed1a29112caff87d53638e0d4c73"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-mate_arm64_2022-09-14_01-15-rootfs.tar.zst
# SHA256SUM=174efdb0995849b1c0c880a6d21f7ffd18a23b246679c3fb9c9c10309a625a64
# BUILD_DATE=20220914
# BUILD_TAG=2022-09-14
# STATUS=completed
# VERSION=latest02
# END_TIME=01:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-14
begin = 2022-09-14 00:28:46.569217196+00:00
start-sync_0 = 00:48:40
start-zstd = 00:54:27
start-sync_1 = 01:14:16
end-sync_1 = 01:15:53
end = 2022-09-14 01:15:53.584794759+00:00

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
