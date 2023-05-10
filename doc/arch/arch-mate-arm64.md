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
tag = ["mate", "2023-05-10"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-mate_arm64_2023-05-10_01-19.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "794e7b2ec5a97d17d093b523e04c67e76a66f012fadbd40f543c9a27720f323b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.1G"
tar_bytes = 5414369792

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1508350991

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230503"
previous_tag = "2023-05-03"
previous_file = "arch-mate_arm64_2023-05-03_01-18-rootfs.tar.zst"
previous_sha256 = "f601eb432e43883ceeca56c8f91d138df8b9fbd94548b93bbdfce86baa12daff"

current_version = "latest01"
current_date = "20230510"
old_file = "arch-mate_arm64_2023-04-26_01-19-rootfs.tar.zst"
old_sha256 = "c02d2d45df1724f29d94e39f4029aa345dcb2a2be87db7ee4f107b150a287808"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-mate_arm64_2023-05-10_01-19-rootfs.tar.zst
# SHA256SUM=794e7b2ec5a97d17d093b523e04c67e76a66f012fadbd40f543c9a27720f323b
# BUILD_DATE=20230510
# BUILD_TAG=2023-05-10
# STATUS=completed
# VERSION=latest01
# END_TIME=01:19

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-10
begin = 2023-05-10 00:31:34.989166187+00:00
start-sync_0 = 00:54:37
start-zstd = 00:59:32
start-sync_1 = 01:18:09
end-sync_1 = 01:19:35
end = 2023-05-10 01:19:35.047566646+00:00

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
