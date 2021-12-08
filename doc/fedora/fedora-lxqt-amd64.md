# fedora-lxqt-amd64

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
    --name fedora-lxqt-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-lxqt-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it fedora-lxqt-amd64 zsh
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

## fedora-lxqt-amd64.toml

```toml
[main]
name = "fedora"
tag = ["lxqt", "2021-12-07"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "fedora-lxqt_amd64_2021-12-07_12-56.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "30cd3a77263d6ef0357f48cce9cb8694a94d8f8aa4f73980c7bc9c0fa08e7885"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.2G"
tar_bytes = 3331578880

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "804M"
zstd_bytes = 842125273

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211102"
previous_tag = ""
previous_file = "fedora-rawhide_amd64+lxqt-2021_11-02-rootfs.tar.zst"
previous_sha256 = "e507e03c2fba7bde2a8166834367ba9a4d407b87840550d3504aab03a9f877c1"

current_version = "latest02"
current_date = "20211207"
old_file = "fedora-rawhide_amd64+lxqt-2021_10-26-rootfs.tar.zst"
old_sha256 = "fc546284d21dbef914c7cafb3d7006b02cae4a8633067745fd826e8f3597cb70"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-lxqt_amd64_2021-12-07_12-56-rootfs.tar.zst
# SHA256SUM=30cd3a77263d6ef0357f48cce9cb8694a94d8f8aa4f73980c7bc9c0fa08e7885
# BUILD_DATE=20211207
# BUILD_TAG=2021-12-07
# STATUS=completed
# VERSION=latest02
# END_TIME=12:56

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-07
begin = 2021-12-07 12:39:53.261755083+00:00
start-sync_0 = 12:44:10
start-zstd = 12:46:49
start-sync_1 = 12:55:55
end-sync_1 = 12:56:53
end = 2021-12-07 12:56:54.012447178+00:00

[server]
repo = "cake233/fedora-lxqt-amd64"

[server.node1]
name = "cn"
current = false
previous = true
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
zsh = 'zsh 5.8 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
