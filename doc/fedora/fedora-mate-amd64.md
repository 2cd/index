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
tag = ["mate", "2022-11-29"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_amd64_2022-11-29_13-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0e842dce0121a00dcec8c372ca9ee06e0bd8e32bc9c8be58c6e980a5c1acb6bc"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.9G"
tar_bytes = 5231015936

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1621889969

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221122"
previous_tag = "2022-11-22"
previous_file = "fedora-mate_amd64_2022-11-22_13-17-rootfs.tar.zst"
previous_sha256 = "dce9cd8a1fb7aee525fb345a02ce2422c03e02cbe727d00b8e561ab0ddc05417"

current_version = "latest01"
current_date = "20221129"
old_file = "fedora-mate_amd64_2022-11-15_13-30-rootfs.tar.zst"
old_sha256 = "8ed058c9fe69c9fada809a7422c2b8a4b2b8e8ffeb3b12931cce01a6d4aa8d13"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-mate_amd64_2022-11-29_13-16-rootfs.tar.zst
# SHA256SUM=0e842dce0121a00dcec8c372ca9ee06e0bd8e32bc9c8be58c6e980a5c1acb6bc
# BUILD_DATE=20221129
# BUILD_TAG=2022-11-29
# STATUS=completed
# VERSION=latest01
# END_TIME=13:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-29
begin = 2022-11-29 12:42:44.375174383+00:00
start-sync_0 = 12:49:26
start-zstd = 12:53:40
start-sync_1 = 13:14:45
end-sync_1 = 13:16:27
end = 2022-11-29 13:16:27.553851835+00:00

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
