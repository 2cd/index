# fedora-xfce-arm64

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
    --name fedora-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-xfce-arm64 zsh
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

## fedora-xfce-arm64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2023-09-26"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_arm64_2023-09-26_15-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "797439dd914553cd8274bb42040bd2acfd7c15f21469f6cc85e7c1eaf218ef97"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.8G"
tar_bytes = 6208396800

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1543145691

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230919"
previous_tag = "2023-09-19"
previous_file = "fedora-xfce_arm64_2023-09-19_14-38-rootfs.tar.zst"
previous_sha256 = "10334232dbb77277fe5f20689ff256a458a352b908a1fe3a1eca37904e91c2b4"

current_version = "latest02"
current_date = "20230926"
old_file = "fedora-xfce_arm64_2023-09-12_13-15-rootfs.tar.zst"
old_sha256 = "f8f3a8533244c7999f633d40001aa727bec062b48534ba8ec1d293538641938d"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-xfce_arm64_2023-09-26_15-05-rootfs.tar.zst
# SHA256SUM=797439dd914553cd8274bb42040bd2acfd7c15f21469f6cc85e7c1eaf218ef97
# BUILD_DATE=20230926
# BUILD_TAG=2023-09-26
# STATUS=completed
# VERSION=latest02
# END_TIME=15:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-26
begin = 2023-09-26 12:53:06.038418242+00:00
start-sync_0 = 14:34:00
start-zstd = 14:40:39
start-sync_1 = 15:03:41
end-sync_1 = 15:05:56
end = 2023-09-26 15:05:56.414329737+00:00

[server]
repo = "cake233/fedora-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.38.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
