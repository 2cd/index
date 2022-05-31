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
tag = ["mate", "2022-05-31"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_amd64_2022-05-31_13-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c66c4f02de3b0d2a9aa09ad4f70ec86b74ce1956d0e35ef6f5f19cec6ce76a67"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.8G"
tar_bytes = 2917842944

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "737M"
zstd_bytes = 772644444

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220524"
previous_tag = "2022-05-24"
previous_file = "fedora-mate_amd64_2022-05-24_12-57-rootfs.tar.zst"
previous_sha256 = "b348c1dee028965f8db4c493781d1ed5f1e51f2765bd8c1382fb73b56e7b9f33"

current_version = "latest02"
current_date = "20220531"
old_file = "fedora-mate_amd64_2022-05-17_13-03-rootfs.tar.zst"
old_sha256 = "6574e04345a80ba6fdcd82b9484c77dc24964b41c9e4d1cb5c2dec5b4a21a9d8"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-mate_amd64_2022-05-31_13-06-rootfs.tar.zst
# SHA256SUM=c66c4f02de3b0d2a9aa09ad4f70ec86b74ce1956d0e35ef6f5f19cec6ce76a67
# BUILD_DATE=20220531
# BUILD_TAG=2022-05-31
# STATUS=completed
# VERSION=latest02
# END_TIME=13:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-31
begin = 2022-05-31 12:47:26.858866713+00:00
start-sync_0 = 12:52:43
start-zstd = 12:55:06
start-sync_1 = 13:05:58
end-sync_1 = 13:06:53
end = 2022-05-31 13:06:53.969201505+00:00

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
