# debian-mate-arm64

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
    --name debian-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-mate-arm64 zsh
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

## debian-mate-arm64.toml

```toml
[main]
name = "debian"
tag = ["mate", "2023-07-19"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-mate_arm64_2023-07-19_13-21.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1c6a35d1b2674a62208838ccea78c01ca2a26eecda9b0606f85205ff5892705c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.9G"
tar_bytes = 5223944192

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1395952889

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230712"
previous_tag = "2023-07-12"
previous_file = "debian-mate_arm64_2023-07-12_13-10-rootfs.tar.zst"
previous_sha256 = "963e8c1838b85a214e4ae8bfb8690b457b97a059cfae265e29d3787e37a85ccd"

current_version = "latest02"
current_date = "20230719"
old_file = "debian-mate_arm64_2023-07-05_13-01-rootfs.tar.zst"
old_sha256 = "dd89d58db88b1dbb2556d63d67009d460d8ea8b29885bfb9287f256d3931a612"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-mate_arm64_2023-07-19_13-21-rootfs.tar.zst
# SHA256SUM=1c6a35d1b2674a62208838ccea78c01ca2a26eecda9b0606f85205ff5892705c
# BUILD_DATE=20230719
# BUILD_TAG=2023-07-19
# STATUS=completed
# VERSION=latest02
# END_TIME=13:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-19
begin = 2023-07-19 12:26:06.776534304+00:00
start-sync_0 = 12:56:46
start-zstd = 13:01:06
start-sync_1 = 13:19:37
end-sync_1 = 13:21:03
end = 2023-07-19 13:21:03.547719693+00:00

[server]
repo = "cake233/debian-mate-arm64"

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
ldd = 'ldd (Debian GLIBC 2.37-6) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
