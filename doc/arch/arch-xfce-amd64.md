# arch-xfce-amd64

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
    --name arch-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it arch-xfce-amd64 zsh
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

## arch-xfce-amd64.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2021-12-08"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "arch-xfce_amd64_2021-12-08_01-45.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "6c27e4f9cc07339f5f82229d0c9e6b1764e1ad30cc811c8974abc030ebf46c10"

# zstd: [1-22]
zstd-level = 15

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3835019776

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1253401554

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211201"
previous_tag = "2021-12-01"
previous_file = "arch-xfce_amd64_2021-12-01_00-43-rootfs.tar.zst"
previous_sha256 = ""

current_version = "latest01"
current_date = "20211208"
old_file = "arch-xfce_amd64_2021-11-28_23-45-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-xfce_amd64_2021-12-08_01-45-rootfs.tar.zst
# SHA256SUM=6c27e4f9cc07339f5f82229d0c9e6b1764e1ad30cc811c8974abc030ebf46c10
# BUILD_DATE=20211208
# BUILD_TAG=2021-12-08
# STATUS=completed
# VERSION=latest01
# END_TIME=01:45

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-08
begin = 2021-12-08 01:28:14.608001969+00:00
start-sync_0 = 01:35:17
start-zstd = 01:38:46
start-sync_1 = 01:43:50
end-sync_1 = 01:45:05
end = 2021-12-08 01:45:05.137962940+00:00

[server]
repo = "cake233/arch-xfce-amd64"

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
zsh = 'zsh 5.8 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
