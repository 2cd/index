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
tag = ["mate", "2022-05-24"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_amd64_2022-05-24_12-57.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b348c1dee028965f8db4c493781d1ed5f1e51f2765bd8c1382fb73b56e7b9f33"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.8G"
tar_bytes = 2918964224

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "738M"
zstd_bytes = 773093532

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220517"
previous_tag = "2022-05-17"
previous_file = "fedora-mate_amd64_2022-05-17_13-03-rootfs.tar.zst"
previous_sha256 = "6574e04345a80ba6fdcd82b9484c77dc24964b41c9e4d1cb5c2dec5b4a21a9d8"

current_version = "latest01"
current_date = "20220524"
old_file = "fedora-mate_amd64_2022-05-10_13-21-rootfs.tar.zst"
old_sha256 = "98d4014ef65d072d16e6891c31983fc3dc8c962ca8027f8c65e260cc9566fde1"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-mate_amd64_2022-05-24_12-57-rootfs.tar.zst
# SHA256SUM=b348c1dee028965f8db4c493781d1ed5f1e51f2765bd8c1382fb73b56e7b9f33
# BUILD_DATE=20220524
# BUILD_TAG=2022-05-24
# STATUS=completed
# VERSION=latest01
# END_TIME=12:57

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-24
begin = 2022-05-24 12:41:43.412508842+00:00
start-sync_0 = 12:45:18
start-zstd = 12:47:07
start-sync_1 = 12:56:30
end-sync_1 = 12:57:17
end = 2022-05-24 12:57:17.584737932+00:00

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
