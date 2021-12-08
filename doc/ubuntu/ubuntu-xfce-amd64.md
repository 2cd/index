# ubuntu-xfce-amd64

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
    --name ubuntu-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it ubuntu-xfce-amd64 zsh
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

## ubuntu-xfce-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2021-12-07", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "ubuntu-xfce_amd64_2021-12-07_00-52.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "52346cbbe773dc2d647901e7c737823dc46c85f65797a643aa48bbcfd6904390"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.8G"
tar_bytes = 2953854464

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "765M"
zstd_bytes = 801434969

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211130"
previous_tag = "2021-11-30"
previous_file = "ubuntu-xfce_amd64_2021-11-30_14-09-rootfs.tar.zst"
previous_sha256 = ""

current_version = "latest02"
current_date = "20211207"
old_file = "ubuntu-xfce-amd64_2021-11-28_21-36-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-xfce_amd64_2021-12-07_00-52-rootfs.tar.zst
# SHA256SUM=52346cbbe773dc2d647901e7c737823dc46c85f65797a643aa48bbcfd6904390
# BUILD_DATE=20211207
# BUILD_TAG=2021-12-07
# STATUS=completed
# VERSION=latest02
# END_TIME=00:52

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-07
begin = 2021-12-07 00:23:08.137274561+00:00
start-sync_0 = 00:40:27
start-zstd = 00:43:14
start-sync_1 = 00:51:59
end-sync_1 = 00:52:56
end = 2021-12-07 00:52:56.444457086+00:00

[server]
repo = "cake233/ubuntu-xfce-amd64"

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
zsh = 'zsh 5.8 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
