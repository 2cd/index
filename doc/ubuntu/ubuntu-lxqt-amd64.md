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

## ubuntu-lxqt-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2023-08-22", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_amd64_2023-08-22_00-52.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "79f3d08b7a33aa1376c350ff07745ddb6baee3d52543e6e15c3f5fcf6d9c2ea7"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.4G"
tar_bytes = 4622980096

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1283068280

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230816"
previous_tag = "2023-08-16"
previous_file = "ubuntu-lxqt_amd64_2023-08-16_15-19-rootfs.tar.zst"
previous_sha256 = "2cc8be993cd3d28d912b167a7d924a26b5dbcbcdae2ce3395c69210e8c47c37e"

current_version = "latest01"
current_date = "20230822"
old_file = "ubuntu-lxqt_amd64_2023-08-15_00-29-rootfs.tar.zst"
old_sha256 = "2a9809b16c936d0b11a3cfa93a51a05fe173320e21eeef45692bf033211ed8c3"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-lxqt_amd64_2023-08-22_00-52-rootfs.tar.zst
# SHA256SUM=79f3d08b7a33aa1376c350ff07745ddb6baee3d52543e6e15c3f5fcf6d9c2ea7
# BUILD_DATE=20230822
# BUILD_TAG=2023-08-22
# STATUS=completed
# VERSION=latest01
# END_TIME=00:52

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-22
begin = 2023-08-22 00:24:05.215276880+00:00
start-sync_0 = 00:30:35
start-zstd = 00:34:29
start-sync_1 = 00:50:49
end-sync_1 = 00:52:13
end = 2023-08-22 00:52:13.622757242+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.37-0ubuntu2) 2.37'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
