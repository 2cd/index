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
tag = ["mate", "2022-06-14"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_amd64_2022-06-14_13-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7db237c59a5dc7ab4ff43768bbd707581730e9a370b1216725e6de00baf13207"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.8G"
tar_bytes = 2935434752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "742M"
zstd_bytes = 777969704

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220607"
previous_tag = "2022-06-07"
previous_file = "fedora-mate_amd64_2022-06-07_12-54-rootfs.tar.zst"
previous_sha256 = "3b84fded2bc1b49b2b3d3b2c4d3d49484b2a1844abba3cf8b1e751067cc5b99c"

current_version = "latest02"
current_date = "20220614"
old_file = "fedora-mate_amd64_2022-05-31_13-06-rootfs.tar.zst"
old_sha256 = "c66c4f02de3b0d2a9aa09ad4f70ec86b74ce1956d0e35ef6f5f19cec6ce76a67"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-mate_amd64_2022-06-14_13-04-rootfs.tar.zst
# SHA256SUM=7db237c59a5dc7ab4ff43768bbd707581730e9a370b1216725e6de00baf13207
# BUILD_DATE=20220614
# BUILD_TAG=2022-06-14
# STATUS=completed
# VERSION=latest02
# END_TIME=13:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-14
begin = 2022-06-14 12:48:13.930483122+00:00
start-sync_0 = 12:52:08
start-zstd = 12:53:59
start-sync_1 = 13:03:56
end-sync_1 = 13:04:44
end = 2022-06-14 13:04:44.230705840+00:00

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
