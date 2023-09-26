# fedora-kde-amd64

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
    --name fedora-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-kde-amd64 zsh
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

## fedora-kde-amd64.toml

```toml
[main]
name = "fedora"
tag = ["kde", "2023-09-26"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_amd64_2023-09-26_13-27.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "978d3a3230712d8e903defe919fc7260c5d79c074be6d300c74f5794330b0831"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.1G"
tar_bytes = 5474768896

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1717292458

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230919"
previous_tag = "2023-09-19"
previous_file = "fedora-kde_amd64_2023-09-19_13-27-rootfs.tar.zst"
previous_sha256 = "9c6bfa4a978f3bba0b5494334d493da8f1b438458e2acb70460edf2b325e64f9"

current_version = "latest02"
current_date = "20230926"
old_file = "fedora-kde_amd64_2023-09-12_12-51-rootfs.tar.zst"
old_sha256 = "c8daf8b4695c438ca24a14900a137ea84fb65cf56e8e1e576295428f7089fd99"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-kde_amd64_2023-09-26_13-27-rootfs.tar.zst
# SHA256SUM=978d3a3230712d8e903defe919fc7260c5d79c074be6d300c74f5794330b0831
# BUILD_DATE=20230926
# BUILD_TAG=2023-09-26
# STATUS=completed
# VERSION=latest02
# END_TIME=13:27

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-26
begin = 2023-09-26 12:53:02.479825572+00:00
start-sync_0 = 12:59:56
start-zstd = 13:04:28
start-sync_1 = 13:24:45
end-sync_1 = 13:27:18
end = 2023-09-26 13:27:18.918103946+00:00

[server]
repo = "cake233/fedora-kde-amd64"

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
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
