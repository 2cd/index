# ubuntu-mate-arm64

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
    --name ubuntu-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-mate-arm64 zsh
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

## ubuntu-mate-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["mate", "2022-07-05", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-mate_arm64_2022-07-05_01-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "849f9bd7bbe491cf8b2e7d726f94c0e46e9213201ea8901f8add03f51b80800e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4191097344

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1144673466

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220628"
previous_tag = "2022-06-28"
previous_file = "ubuntu-mate_arm64_2022-06-28_01-06-rootfs.tar.zst"
previous_sha256 = "a19f66dfbfa0a8f93dc2aa0caa43eb898fdde8a82c934f935b463110bf1d1939"

current_version = "latest02"
current_date = "20220705"
old_file = "ubuntu-mate_arm64_2022-06-21_01-02-rootfs.tar.zst"
old_sha256 = "5df15be8d34cb6eeb56215ad704e56c2972c1b8f0e0b16a9b23068045fe65bd4"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-mate_arm64_2022-07-05_01-10-rootfs.tar.zst
# SHA256SUM=849f9bd7bbe491cf8b2e7d726f94c0e46e9213201ea8901f8add03f51b80800e
# BUILD_DATE=20220705
# BUILD_TAG=2022-07-05
# STATUS=completed
# VERSION=latest02
# END_TIME=01:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-05
begin = 2022-07-05 00:18:25.426976981+00:00
start-sync_0 = 00:50:00
start-zstd = 00:53:52
start-sync_1 = 01:08:47
end-sync_1 = 01:10:04
end = 2022-07-05 01:10:04.442724789+00:00

[server]
repo = "cake233/ubuntu-mate-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
