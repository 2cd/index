# debian-mate-amd64

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
    --name debian-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-mate-amd64 zsh
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

## debian-mate-amd64.toml

```toml
[main]
name = "debian"
tag = ["mate", "2023-03-29"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-mate_amd64_2023-03-29_12-44.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5b69b8f24e4c967d79110363490010b6d951d5f8afbd39229a33111edcbe8d89"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.9G"
tar_bytes = 4105954816

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1115727653

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230322"
previous_tag = "2023-03-22"
previous_file = "debian-mate_amd64_2023-03-22_12-48-rootfs.tar.zst"
previous_sha256 = "831d1ce0ca909002640a4374fc8bb57c0ca6164e405204b4b472e32fc5cf26c2"

current_version = "latest02"
current_date = "20230329"
old_file = "debian-mate_amd64_2023-03-15_12-45-rootfs.tar.zst"
old_sha256 = "50c0af4f93d2f6ff7a33a496fd2ad5494a254850e91a0a99a412db828df28ee2"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-mate_amd64_2023-03-29_12-44-rootfs.tar.zst
# SHA256SUM=5b69b8f24e4c967d79110363490010b6d951d5f8afbd39229a33111edcbe8d89
# BUILD_DATE=20230329
# BUILD_TAG=2023-03-29
# STATUS=completed
# VERSION=latest02
# END_TIME=12:44

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-29
begin = 2023-03-29 12:21:07.600689609+00:00
start-sync_0 = 12:26:07
start-zstd = 12:29:36
start-sync_1 = 12:43:23
end-sync_1 = 12:44:26
end = 2023-03-29 12:44:26.800960169+00:00

[server]
repo = "cake233/debian-mate-amd64"

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
