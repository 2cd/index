# ubuntu-xfce-arm64

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
    --name ubuntu-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-xfce-arm64 zsh
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

## ubuntu-xfce-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2022-10-25", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_arm64_2022-10-25_01-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "84e1e32033f8150041e1d1e89e273a655d1b7c6c062b50ba5b7c1b095db391cc"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3855507456

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1009M"
zstd_bytes = 1057228300

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221018"
previous_tag = "2022-10-18"
previous_file = "ubuntu-xfce_arm64_2022-10-18_01-11-rootfs.tar.zst"
previous_sha256 = "da6b1e06b18c5e2c54026ed353acd0ee3930cd4284d5501a7cc232f8a1d9d55a"

current_version = "latest02"
current_date = "20221025"
old_file = "ubuntu-xfce_arm64_2022-10-11_01-18-rootfs.tar.zst"
old_sha256 = "5961a944652ac780bffe3f81d25c4b74efc09cffcde0adf8f9cbc7c55be39d45"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-xfce_arm64_2022-10-25_01-17-rootfs.tar.zst
# SHA256SUM=84e1e32033f8150041e1d1e89e273a655d1b7c6c062b50ba5b7c1b095db391cc
# BUILD_DATE=20221025
# BUILD_TAG=2022-10-25
# STATUS=completed
# VERSION=latest02
# END_TIME=01:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-25
begin = 2022-10-25 00:23:07.410422411+00:00
start-sync_0 = 00:57:16
start-zstd = 01:00:33
start-sync_1 = 01:16:01
end-sync_1 = 01:17:18
end = 2022-10-25 01:17:18.358712227+00:00

[server]
repo = "cake233/ubuntu-xfce-arm64"

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
