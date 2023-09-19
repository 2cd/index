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
tag = ["kde", "2023-09-19", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_armhf_2023-09-19_01-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ddebfc9b83318277354bdfab173682a095879927ad4fac19aad2e5d2d54ecff7"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.9G"
tar_bytes = 4093031936

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1310990284

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230912"
previous_tag = "2023-09-12"
previous_file = "ubuntu-kde_armhf_2023-09-12_01-15-rootfs.tar.zst"
previous_sha256 = "1e6732e55ee2b2881059dcb312dcea88062ae17f518d55fc8fe65a2d7fe8cf96"

current_version = "latest02"
current_date = "20230919"
old_file = "ubuntu-kde_armhf_2023-09-05_01-20-rootfs.tar.zst"
old_sha256 = "88142338f3a2bf0afca0697e03123f738c081cc55c5a6c31de0f7955a5639935"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-kde_armhf_2023-09-19_01-17-rootfs.tar.zst
# SHA256SUM=ddebfc9b83318277354bdfab173682a095879927ad4fac19aad2e5d2d54ecff7
# BUILD_DATE=20230919
# BUILD_TAG=2023-09-19
# STATUS=completed
# VERSION=latest02
# END_TIME=01:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-19
begin = 2023-09-19 00:27:56.581217962+00:00
start-sync_0 = 01:00:39
start-zstd = 01:03:43
start-sync_1 = 01:16:14
end-sync_1 = 01:17:31
end = 2023-09-19 01:17:31.153673864+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu4) 2.38'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
