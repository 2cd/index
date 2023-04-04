# fedora-kde-arm64

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
    --name fedora-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-kde-arm64 zsh
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

## fedora-kde-arm64.toml

```toml
[main]
name = "fedora"
tag = ["kde", "2023-04-04"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_arm64_2023-04-04_15-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b7fd2267c5e9e97e1408a3f21edbfb3b5adbf1502779b5bd10f07e5f1b5bde5a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.9G"
tar_bytes = 7386579456

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.8G"
zstd_bytes = 1926783148

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230328"
previous_tag = "2023-03-28"
previous_file = "fedora-kde_arm64_2023-03-28_15-10-rootfs.tar.zst"
previous_sha256 = "b7d9932ae1dc238210c573e8fc058450c8ef91d8d3b2c04c294a56867bfcb930"

current_version = "latest01"
current_date = "20230404"
old_file = "fedora-kde_arm64_2023-03-21_15-26-rootfs.tar.zst"
old_sha256 = "dc6eef2800aefb308378ec26bf0706ad9b2577f9b4247a6bafbfc10f1cf0a5b2"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-kde_arm64_2023-04-04_15-03-rootfs.tar.zst
# SHA256SUM=b7fd2267c5e9e97e1408a3f21edbfb3b5adbf1502779b5bd10f07e5f1b5bde5a
# BUILD_DATE=20230404
# BUILD_TAG=2023-04-04
# STATUS=completed
# VERSION=latest01
# END_TIME=15:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-04
begin = 2023-04-04 12:55:41.712073496+00:00
start-sync_0 = 14:34:28
start-zstd = 14:39:41
start-sync_1 = 15:01:57
end-sync_1 = 15:03:54
end = 2023-04-04 15:03:54.952205589+00:00

[server]
repo = "cake233/fedora-kde-arm64"

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
ldd = 'ldd (GNU libc) 2.37.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
