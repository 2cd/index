# fedora-lxqt-arm64

## How to run it?

```shell
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
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
    --name fedora-lxqt-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-lxqt-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it fedora-lxqt-arm64 zsh
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

## fedora-lxqt-arm64.toml

```toml
[main]
name = "fedora"
tag = ["lxqt", "2021-11-30"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "fedora-lxqt_arm64_2021-11-30_13-39.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "29ae4141b84b69a8093528d3908a8db7cd2349c08e5fa1f6acfeee098ed0cb77"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.4G"
tar_bytes = 4670795264

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "967M"
zstd_bytes = 1013490097

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211102"
last_tag = ""
last_file = "fedora-rawhide_arm64+lxqt-2021_11-02-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211130"
old_file = "fedora-rawhide_arm64+lxqt-2021_10-26-rootfs.tar.zst"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-lxqt_arm64_2021-11-30_13-39-rootfs.tar.zst
# BUILD_DATE=20211130
# BUILD_TAG=2021-11-30
# STATUS=completed
# VERSION=latest02
# END_TIME=13:39

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-30
begin = 2021-11-30 12:43:09.358556640+00:00
start-sync_0 = 13:23:40
start-zstd = 13:26:55
start-sync_1 = 13:38:23
end-sync_1 = 13:39:24
end = 2021-11-30 13:39:24.248626018+00:00

[server]
repo = "cake233/fedora-lxqt-arm64"

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
zsh = 'zsh 5.8 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
