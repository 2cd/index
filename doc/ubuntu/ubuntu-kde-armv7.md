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

## ubuntu-kde-armv7.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2022-01-04", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "ubuntu-kde_armhf_2022-01-04_01-14.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "b2dfc54bfafe1f6ccec5fa70b182182464650a150450964dfacaf42b8dc90b6b"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3197529600

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1021M"
zstd_bytes = 1069930094

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211228"
previous_tag = "2021-12-28"
previous_file = "ubuntu-kde_armhf_2021-12-28_01-09-rootfs.tar.zst"
previous_sha256 = "01e6975001d0655fef62863a25f899dbfedfd7924e03e58419a19609377fb830"

current_version = "latest01"
current_date = "20220104"
old_file = "ubuntu-kde_armhf_2021-12-21_01-16-rootfs.tar.zst"
old_sha256 = "7d98580a78ccc57cb59569811ed93869c63ac40f30bc39194aee3f6e3ffc95c8"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-kde_armhf_2022-01-04_01-14-rootfs.tar.zst
# SHA256SUM=b2dfc54bfafe1f6ccec5fa70b182182464650a150450964dfacaf42b8dc90b6b
# BUILD_DATE=20220104
# BUILD_TAG=2022-01-04
# STATUS=completed
# VERSION=latest01
# END_TIME=01:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-04
begin = 2022-01-04 00:22:40.425957339+00:00
start-sync_0 = 01:01:42
start-zstd = 01:04:37
start-sync_1 = 01:13:21
end-sync_1 = 01:14:33
end = 2022-01-04 01:14:33.790699259+00:00

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
zsh = 'zsh 5.8 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
