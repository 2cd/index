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

## fedora-mate-amd64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2022-03-29"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "fedora-mate_amd64_2022-03-29_12-12.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "e44b27a78dda2502bb186d9122ef6e881991363ecd957f1d074965e3fab74c37"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.7G"
tar_bytes = 2802993152

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "702M"
zstd_bytes = 735786080

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220322"
previous_tag = "2022-03-22"
previous_file = "fedora-mate_amd64_2022-03-22_12-52-rootfs.tar.zst"
previous_sha256 = "cd5517db338052d71913abc8e7b160d29845579fe2ab1ffe4f9fda7ca262ae19"

current_version = "latest01"
current_date = "20220329"
old_file = "fedora-mate_amd64_2022-03-15_13-18-rootfs.tar.zst"
old_sha256 = "5c2fa88621c2bf9edf1eebdb3611b6d92a2cf1349b2d8e900d4f03790ecb4a08"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-mate_amd64_2022-03-29_12-12-rootfs.tar.zst
# SHA256SUM=e44b27a78dda2502bb186d9122ef6e881991363ecd957f1d074965e3fab74c37
# BUILD_DATE=20220329
# BUILD_TAG=2022-03-29
# STATUS=completed
# VERSION=latest01
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-29
begin = 2022-03-29 11:52:08.885661996+00:00
start-sync_0 = 11:56:50
start-zstd = 11:59:09
start-sync_1 = 12:11:31
end-sync_1 = 12:12:22
end = 2022-03-29 12:12:22.806448039+00:00

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.8.1 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
