# ubuntu-kde-arm64

## How to run it?

```sh
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
    --name ubuntu-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-arm64 zsh
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

## ubuntu-kde-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2023-02-21", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_arm64_2023-02-21_01-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8a9d5af87d7c10037895945afd43ff01fb0468d5c7ccb3bb53279b11a80af40c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.8G"
tar_bytes = 5052766720

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1377895032

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230214"
previous_tag = "2023-02-14"
previous_file = "ubuntu-kde_arm64_2023-02-14_01-04-rootfs.tar.zst"
previous_sha256 = "3df59809790a31a9fe1ecc1681a4f2c79cb64e77a96c91789c21c4836df70087"

current_version = "latest02"
current_date = "20230221"
old_file = "ubuntu-kde_arm64_2023-02-07_01-03-rootfs.tar.zst"
old_sha256 = "d623388f0bd76b2b83fe27106282f951fc6180d6a747b5a9f653596e0e081ad0"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-kde_arm64_2023-02-21_01-08-rootfs.tar.zst
# SHA256SUM=8a9d5af87d7c10037895945afd43ff01fb0468d5c7ccb3bb53279b11a80af40c
# BUILD_DATE=20230221
# BUILD_TAG=2023-02-21
# STATUS=completed
# VERSION=latest02
# END_TIME=01:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-21
begin = 2023-02-21 00:03:20.026153014+00:00
start-sync_0 = 00:43:20
start-zstd = 00:47:54
start-sync_1 = 01:06:57
end-sync_1 = 01:08:20
end = 2023-02-21 01:08:20.840755511+00:00

[server]
repo = "cake233/ubuntu-kde-arm64"

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
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
