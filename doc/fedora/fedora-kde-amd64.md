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
tag = ["kde", "2022-07-05"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_amd64_2022-07-05_13-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "89e77842b9845b76aaeebb56be6aa79c78cb68d768cb87258c681ad611a5cabc"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.7G"
tar_bytes = 4973177344

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1549788598

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220628"
previous_tag = "2022-06-28"
previous_file = "fedora-kde_amd64_2022-06-28_13-16-rootfs.tar.zst"
previous_sha256 = "7f4e37c0b75689c4564bda99d3ac147500e26e304b8882077dbb2ab0fbfe0bbb"

current_version = "latest01"
current_date = "20220705"
old_file = "fedora-kde_amd64_2022-06-21_13-32-rootfs.tar.zst"
old_sha256 = "aa66d6f50be1b56bee8ec6a3554cb9af4b8b955fb6ca3476d574a8c2255fe834"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-kde_amd64_2022-07-05_13-11-rootfs.tar.zst
# SHA256SUM=89e77842b9845b76aaeebb56be6aa79c78cb68d768cb87258c681ad611a5cabc
# BUILD_DATE=20220705
# BUILD_TAG=2022-07-05
# STATUS=completed
# VERSION=latest01
# END_TIME=13:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-05
begin = 2022-07-05 12:42:41.213307448+00:00
start-sync_0 = 12:49:05
start-zstd = 12:53:09
start-sync_1 = 13:10:07
end-sync_1 = 13:11:49
end = 2022-07-05 13:11:49.967248437+00:00

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
