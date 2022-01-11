# ubuntu-mate-amd64

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
    --name ubuntu-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-mate-amd64 zsh
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

## ubuntu-mate-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["mate", "2022-01-11", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "ubuntu-mate_amd64_2022-01-11_00-41.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "4e0f553c3a8f5eea58329ba6082ebcc2a6edc6a5f9be3ce42d6508807c9f5d31"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.3G"
tar_bytes = 3475052544

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "878M"
zstd_bytes = 919885548

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220104"
previous_tag = "2022-01-04"
previous_file = "ubuntu-mate_amd64_2022-01-04_00-40-rootfs.tar.zst"
previous_sha256 = "4a03c5a7f4f94d34ac3320eb80fbb53a707c3067c9f58bbbe87b177b72d53c25"

current_version = "latest01"
current_date = "20220111"
old_file = "ubuntu-mate_amd64_2021-12-28_00-41-rootfs.tar.zst"
old_sha256 = "8c95cd38c4cc7e84b1af4c858e5a37584fe512372b2cb8db75910e466e9e4cd0"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-mate_amd64_2022-01-11_00-41-rootfs.tar.zst
# SHA256SUM=4e0f553c3a8f5eea58329ba6082ebcc2a6edc6a5f9be3ce42d6508807c9f5d31
# BUILD_DATE=20220111
# BUILD_TAG=2022-01-11
# STATUS=completed
# VERSION=latest01
# END_TIME=00:41

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-11
begin = 2022-01-11 00:23:14.382147785+00:00
start-sync_0 = 00:28:34
start-zstd = 00:31:25
start-sync_1 = 00:40:07
end-sync_1 = 00:41:05
end = 2022-01-11 00:41:05.284951453+00:00

[server]
repo = "cake233/ubuntu-mate-amd64"

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
