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
tag = ["kde", "2023-04-11"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_arm64_2023-04-11_15-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0298c9f3455ce8f4caa1ce0c87cade761468c488599210ec6cb72eac3bff24c9"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.9G"
tar_bytes = 7388675584

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.8G"
zstd_bytes = 1928325551

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230404"
previous_tag = "2023-04-04"
previous_file = "fedora-kde_arm64_2023-04-04_15-03-rootfs.tar.zst"
previous_sha256 = "b7fd2267c5e9e97e1408a3f21edbfb3b5adbf1502779b5bd10f07e5f1b5bde5a"

current_version = "latest02"
current_date = "20230411"
old_file = "fedora-kde_arm64_2023-03-28_15-10-rootfs.tar.zst"
old_sha256 = "b7d9932ae1dc238210c573e8fc058450c8ef91d8d3b2c04c294a56867bfcb930"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-kde_arm64_2023-04-11_15-11-rootfs.tar.zst
# SHA256SUM=0298c9f3455ce8f4caa1ce0c87cade761468c488599210ec6cb72eac3bff24c9
# BUILD_DATE=20230411
# BUILD_TAG=2023-04-11
# STATUS=completed
# VERSION=latest02
# END_TIME=15:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-11
begin = 2023-04-11 12:58:54.744450498+00:00
start-sync_0 = 14:41:53
start-zstd = 14:47:10
start-sync_1 = 15:09:41
end-sync_1 = 15:11:41
end = 2023-04-11 15:11:41.293570033+00:00

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
