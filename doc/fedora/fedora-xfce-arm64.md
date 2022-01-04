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

## fedora-xfce-arm64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2022-01-04"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "fedora-xfce_arm64_2022-01-04_14-15.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "ee9e15aeecabbecef736e7f008a8cfeba752eb2181bee0ca5fb3cab1dafa6d92"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.1G"
tar_bytes = 5419376640

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1492509120

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211228"
previous_tag = "2021-12-28"
previous_file = "fedora-xfce_arm64_2021-12-28_14-20-rootfs.tar.zst"
previous_sha256 = "a9b5465cc7c9c354b948503a3de2c1139d171d71704b71c120cfe4cca0701ea7"

current_version = "latest01"
current_date = "20220104"
old_file = "fedora-xfce_arm64_2021-12-21_14-07-rootfs.tar.zst"
old_sha256 = "3d3927fe49a8329ab56190a6b68e30e639bd57787b6390bf7e476c8af2d6d90c"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-xfce_arm64_2022-01-04_14-15-rootfs.tar.zst
# SHA256SUM=ee9e15aeecabbecef736e7f008a8cfeba752eb2181bee0ca5fb3cab1dafa6d92
# BUILD_DATE=20220104
# BUILD_TAG=2022-01-04
# STATUS=completed
# VERSION=latest01
# END_TIME=14:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-04
begin = 2022-01-04 12:50:02.271776185+00:00
start-sync_0 = 13:54:54
start-zstd = 14:00:06
start-sync_1 = 14:14:19
end-sync_1 = 14:15:55
end = 2022-01-04 14:15:55.865069858+00:00

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
ldd = 'ldd (GNU libc) 2.34.9000'
zsh = 'zsh 5.8 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
