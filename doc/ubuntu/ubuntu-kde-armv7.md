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
tag = ["kde", "2022-11-22", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_armhf_2022-11-22_00-49.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e844fe648295754986e7b2b66605a8e05fd432e2489f36936d1db03bd4ff8c24"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 4037185536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1230191892

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221115"
previous_tag = "2022-11-15"
previous_file = "ubuntu-kde_armhf_2022-11-15_01-01-rootfs.tar.zst"
previous_sha256 = "bd67f88875d808f7f812cc034dddad2ab67b8f5bacd2cdc4af13cd8a22f3c487"

current_version = "latest02"
current_date = "20221122"
old_file = "ubuntu-kde_armhf_2022-11-08_00-49-rootfs.tar.zst"
old_sha256 = "0bcffeaecb201868e209aa6b038cc929036cfb69e02676a17c6649ab671b526e"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-kde_armhf_2022-11-22_00-49-rootfs.tar.zst
# SHA256SUM=e844fe648295754986e7b2b66605a8e05fd432e2489f36936d1db03bd4ff8c24
# BUILD_DATE=20221122
# BUILD_TAG=2022-11-22
# STATUS=completed
# VERSION=latest02
# END_TIME=00:49

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-22
begin = 2022-11-22 00:03:01.899765731+00:00
start-sync_0 = 00:33:23
start-zstd = 00:36:32
start-sync_1 = 00:48:17
end-sync_1 = 00:49:25
end = 2022-11-22 00:49:25.291668408+00:00

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
