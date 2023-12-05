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
tag = ["kde", "2023-12-05", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_armhf_2023-12-05_01-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f63753f1bc57519886c890fff16eb50820f7592f647306a845247c5c8b0ea9c1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.9G"
tar_bytes = 4107928576

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1313577237

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231121"
previous_tag = "2023-11-21"
previous_file = "ubuntu-kde_armhf_2023-11-21_01-06-rootfs.tar.zst"
previous_sha256 = "f7ab61c80e693ec489d4dedc2573f89c16d22860a601e86e2f7a855cd6887750"

current_version = "latest01"
current_date = "20231205"
old_file = "ubuntu-kde_armhf_2023-11-14_01-04-rootfs.tar.zst"
old_sha256 = "b4bce76ef05511e6a0b2651f5a62e4dae10fcd2875b1ea41147065c08ad556b8"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-kde_armhf_2023-12-05_01-16-rootfs.tar.zst
# SHA256SUM=f63753f1bc57519886c890fff16eb50820f7592f647306a845247c5c8b0ea9c1
# BUILD_DATE=20231205
# BUILD_TAG=2023-12-05
# STATUS=completed
# VERSION=latest01
# END_TIME=01:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-05
begin = 2023-12-05 00:37:31.680938756+00:00
start-sync_0 = 01:02:58
start-zstd = 01:05:08
start-sync_1 = 01:15:48
end-sync_1 = 01:16:49
end = 2023-12-05 01:16:49.458912737+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.38-3ubuntu1) 2.38'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
