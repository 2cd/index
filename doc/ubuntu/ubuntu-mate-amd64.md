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
tag = ["mate", "2022-03-01", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "ubuntu-mate_amd64_2022-03-01_00-47.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "aaef37de7247e1eb3de3a23779f4a9abb495853ffb306ab344a004f551a7301c"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.3G"
tar_bytes = 3540835328

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "891M"
zstd_bytes = 933746273

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220222"
previous_tag = "2022-02-22"
previous_file = "ubuntu-mate_amd64_2022-02-22_00-42-rootfs.tar.zst"
previous_sha256 = "7f85e8715a584b44a4363c9fa7746f1ab877337e0f9f4a72fe31597bbdd01575"

current_version = "latest02"
current_date = "20220301"
old_file = "ubuntu-mate_amd64_2022-02-15_00-39-rootfs.tar.zst"
old_sha256 = "1497a740bf803ffa368b878208a4cca2ebf2b3f5ff5923907b6b729824864f34"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-mate_amd64_2022-03-01_00-47-rootfs.tar.zst
# SHA256SUM=aaef37de7247e1eb3de3a23779f4a9abb495853ffb306ab344a004f551a7301c
# BUILD_DATE=20220301
# BUILD_TAG=2022-03-01
# STATUS=completed
# VERSION=latest02
# END_TIME=00:47

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-01
begin = 2022-03-01 00:24:21.635074212+00:00
start-sync_0 = 00:31:18
start-zstd = 00:34:53
start-sync_1 = 00:45:55
end-sync_1 = 00:47:06
end = 2022-03-01 00:47:07.020584304+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu1) 2.35'
zsh = 'zsh 5.8.1 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
