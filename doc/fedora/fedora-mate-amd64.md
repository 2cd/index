# fedora-mate-amd64

## How to run it?

```shell
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

```shell
    docker exex -it fedora-mate-amd64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```shell
    startvnc
```

or

```shell
    startx11vnc
```

or

```shell
    novnc
```

Note:

If you want to use novnc, then open your browser, and type the address:

```
localhost:36081
```

If you want to use tiger/x11vnc, then open vnc viewer, then type the address:

```
localhost:5903
```

## fedora-mate-amd64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2021-11-30"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "fedora-mate_amd64_2021-11-30_13-15.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "c63a4395fd330d4c25010cfcc5d2193d41d2c19286e24ed1df6bae52cc9695cb"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.4G"
tar_bytes = 4719636992

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1439282061

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211128"
last_tag = "2021-11-28"
last_file = "fedora-mate-amd64_2021-11-28_22-30-rootfs.tar.zst"

current_version = "latest01"
current_date = "20211130"
old_file = "fedora-rawhide_amd64+mate-2021_11-02-rootfs.tar.zst"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-mate_amd64_2021-11-30_13-15-rootfs.tar.zst
# BUILD_DATE=20211130
# BUILD_TAG=2021-11-30
# STATUS=completed
# VERSION=latest01
# END_TIME=13:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-30
begin = 2021-11-30 12:43:12.870707835+00:00
start-sync_0 = 12:53:57
start-zstd = 12:59:08
start-sync_1 = 13:14:07
end-sync_1 = 13:15:44
end = 2021-11-30 13:15:44.889172030+00:00

[server]
repo = "cake233/fedora-mate-amd64"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "us"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "global"
current = false
last = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"

[version]
zsh = 'zsh 5.8 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
