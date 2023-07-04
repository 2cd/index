# ubuntu-kde-armv7

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not armv7, then install qemu & binfmt-support.
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
    --name ubuntu-kde-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-armv7 zsh
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

## ubuntu-kde-armv7.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2023-07-04", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_armhf_2023-07-04_00-56.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "253bbc799dfb866b1ece1495e01eb2b9631897bc9bb323a6ea6b3c1134b00af8"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 4046527488

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1232047331

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230627"
previous_tag = "2023-06-27"
previous_file = "ubuntu-kde_armhf_2023-06-27_00-53-rootfs.tar.zst"
previous_sha256 = "66649c6d45753f2b564e82c1dfca2dbe10f52caf29770d4e253bf4a38af3dc73"

current_version = "latest01"
current_date = "20230704"
old_file = "ubuntu-kde_armhf_2023-06-20_01-01-rootfs.tar.zst"
old_sha256 = "35d37484435a0a190190c28eda91fbd3ab1eaef54af5d037a5828885ebe54320"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-kde_armhf_2023-07-04_00-56-rootfs.tar.zst
# SHA256SUM=253bbc799dfb866b1ece1495e01eb2b9631897bc9bb323a6ea6b3c1134b00af8
# BUILD_DATE=20230704
# BUILD_TAG=2023-07-04
# STATUS=completed
# VERSION=latest01
# END_TIME=00:56

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-04
begin = 2023-07-04 00:03:16.198092421+00:00
start-sync_0 = 00:38:27
start-zstd = 00:41:50
start-sync_1 = 00:54:53
end-sync_1 = 00:56:09
end = 2023-07-04 00:56:09.226008446+00:00

[server]
repo = "cake233/ubuntu-kde-armv7"

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
