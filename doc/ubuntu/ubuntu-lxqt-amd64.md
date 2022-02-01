# ubuntu-lxqt-amd64

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
    --name ubuntu-lxqt-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-lxqt-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-lxqt-amd64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```sh
    startvnc
```

or

```sh
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

## ubuntu-lxqt-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2022-02-01", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "ubuntu-lxqt_amd64_2022-02-01_00-46.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "532d980c761e805abdfd8a533b0f05f492526e62474f5e7680024d7afc61a83c"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.1G"
tar_bytes = 3305137664

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "838M"
zstd_bytes = 878145653

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220125"
previous_tag = "2022-01-25"
previous_file = "ubuntu-lxqt_amd64_2022-01-25_00-43-rootfs.tar.zst"
previous_sha256 = "2eaa1afe41f762933e5cae72b84087a408bc10a31fecdbdd16033d3c7edbbcfc"

current_version = "latest02"
current_date = "20220201"
old_file = "ubuntu-lxqt_amd64_2022-01-18_00-38-rootfs.tar.zst"
old_sha256 = "c340625c762b15150b65a16f82d3ccb034b4d5213b71376f8bb2bc65141081aa"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-lxqt_amd64_2022-02-01_00-46-rootfs.tar.zst
# SHA256SUM=532d980c761e805abdfd8a533b0f05f492526e62474f5e7680024d7afc61a83c
# BUILD_DATE=20220201
# BUILD_TAG=2022-02-01
# STATUS=completed
# VERSION=latest02
# END_TIME=00:46

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-01
begin = 2022-02-01 00:27:27.549856411+00:00
start-sync_0 = 00:33:57
start-zstd = 00:36:56
start-sync_1 = 00:45:06
end-sync_1 = 00:46:08
end = 2022-02-01 00:46:08.715787969+00:00

[server]
repo = "cake233/ubuntu-lxqt-amd64"

[server.node1]
name = "cn"
current = false
previous = false
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
ldd = 'ldd (Ubuntu GLIBC 2.34-0ubuntu3) 2.34'
zsh = 'zsh 5.8 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
