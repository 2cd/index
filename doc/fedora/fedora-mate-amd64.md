# fedora-mate-amd64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not amd64, then install qemu & binfmt-support.
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
    --name fedora-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-amd64 zsh
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

## fedora-mate-amd64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2022-01-04"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "fedora-mate_amd64_2022-01-04_13-16.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "7507356286cd4e80b656d0065f079c93769893c68c5c76e6d666f72dd224b4d3"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4769784832

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1490376360

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211228"
previous_tag = "2021-12-28"
previous_file = "fedora-mate_amd64_2021-12-28_13-09-rootfs.tar.zst"
previous_sha256 = "8e2a33e2c3e732f1524305178e53fc47a6117c4d8b5443728e0f1558beb7d610"

current_version = "latest02"
current_date = "20220104"
old_file = "fedora-mate_amd64_2021-12-21_13-17-rootfs.tar.zst"
old_sha256 = "faec6d2104a9c53848785f7914a1ce179f808bc330d2db7980538428b3d44791"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-mate_amd64_2022-01-04_13-16-rootfs.tar.zst
# SHA256SUM=7507356286cd4e80b656d0065f079c93769893c68c5c76e6d666f72dd224b4d3
# BUILD_DATE=20220104
# BUILD_TAG=2022-01-04
# STATUS=completed
# VERSION=latest02
# END_TIME=13:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-04
begin = 2022-01-04 12:50:03.545966981+00:00
start-sync_0 = 12:56:08
start-zstd = 13:00:20
start-sync_1 = 13:14:30
end-sync_1 = 13:16:02
end = 2022-01-04 13:16:02.107368990+00:00

[server]
repo = "cake233/fedora-mate-amd64"

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
zsh = 'zsh 5.8 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
