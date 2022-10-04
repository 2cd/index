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
tag = ["mate", "2022-10-04"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_amd64_2022-10-04_13-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b818cb5a48908e31e9a5da99ffe1a1540ee5b18afff1161bfabaeed40dd84f42"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.9G"
tar_bytes = 5195115520

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1631349477

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220927"
previous_tag = "2022-09-27"
previous_file = "fedora-mate_amd64_2022-09-27_13-27-rootfs.tar.zst"
previous_sha256 = "824af65d6f194cafd984a1e63dbbd86fb11f031fe0cf2bcdf3159c666677e269"

current_version = "latest01"
current_date = "20221004"
old_file = "fedora-mate_amd64_2022-09-20_13-32-rootfs.tar.zst"
old_sha256 = "61af7f985285cad6387e4fac2371aa847b12a08df5a8f0f7a828df39c348de74"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-mate_amd64_2022-10-04_13-20-rootfs.tar.zst
# SHA256SUM=b818cb5a48908e31e9a5da99ffe1a1540ee5b18afff1161bfabaeed40dd84f42
# BUILD_DATE=20221004
# BUILD_TAG=2022-10-04
# STATUS=completed
# VERSION=latest01
# END_TIME=13:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-04
begin = 2022-10-04 12:49:38.161739206+00:00
start-sync_0 = 12:56:23
start-zstd = 13:00:44
start-sync_1 = 13:18:36
end-sync_1 = 13:20:41
end = 2022-10-04 13:20:41.690680321+00:00

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
