# fedora-xfce-amd64

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
    --name fedora-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-xfce-amd64 zsh
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

## fedora-xfce-amd64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2023-06-27"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_amd64_2023-06-27_13-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0ddbfffb19e01ffe57c5a6cca2307245afb547cd421fe874db1ece97691878af"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.2G"
tar_bytes = 3413719552

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "910M"
zstd_bytes = 954124538

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230620"
previous_tag = "2023-06-20"
previous_file = "fedora-xfce_amd64_2023-06-20_13-16-rootfs.tar.zst"
previous_sha256 = "933d16c1da3b268955e0b8709417bd2ac57d16d726e91135a2418ef09bc92c76"

current_version = "latest02"
current_date = "20230627"
old_file = "fedora-xfce_amd64_2023-06-13_13-24-rootfs.tar.zst"
old_sha256 = "28831c37f881b44b379874c63dacef8d86bea68fc206e8e4a9d224705a6db416"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-xfce_amd64_2023-06-27_13-05-rootfs.tar.zst
# SHA256SUM=0ddbfffb19e01ffe57c5a6cca2307245afb547cd421fe874db1ece97691878af
# BUILD_DATE=20230627
# BUILD_TAG=2023-06-27
# STATUS=completed
# VERSION=latest02
# END_TIME=13:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-27
begin = 2023-06-27 12:48:35.900709660+00:00
start-sync_0 = 12:51:41
start-zstd = 12:53:35
start-sync_1 = 13:04:52
end-sync_1 = 13:05:50
end = 2023-06-27 13:05:50.835622475+00:00

[server]
repo = "cake233/fedora-xfce-amd64"

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
ldd = 'ldd (GNU libc) 2.37.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
