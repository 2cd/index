# debian-lxde-armv7

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
    --name debian-lxde-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-lxde-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-lxde-armv7 zsh
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

## debian-lxde-armv7.toml

```toml
[main]
name = "debian"
tag = ["lxde", "2023-01-04"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_armhf_2023-01-04_13-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9aed81ba04c785fcf32f07006868d9f0d50365403c990ab09e67aa0e91c5344d"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3173659136

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "939M"
zstd_bytes = 983932199

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221228"
previous_tag = "2022-12-28"
previous_file = "debian-lxde_armhf_2022-12-28_12-57-rootfs.tar.zst"
previous_sha256 = "9b9cbb86cb9629647ea6551171e8ad5117e71a363e1e9d23145a885eb4502d11"

current_version = "latest01"
current_date = "20230104"
old_file = "debian-lxde_armhf_2022-12-21_12-54-rootfs.tar.zst"
old_sha256 = "3a2142f8d874cf9903cc4993af22406a948403242ad76002db5184ad22af2f52"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2023-01-04_13-09-rootfs.tar.zst
# SHA256SUM=9aed81ba04c785fcf32f07006868d9f0d50365403c990ab09e67aa0e91c5344d
# BUILD_DATE=20230104
# BUILD_TAG=2023-01-04
# STATUS=completed
# VERSION=latest01
# END_TIME=13:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-04
begin = 2023-01-04 12:24:54.348906101+00:00
start-sync_0 = 12:55:07
start-zstd = 12:57:33
start-sync_1 = 13:08:18
end-sync_1 = 13:09:29
end = 2023-01-04 13:09:29.575464510+00:00

[server]
repo = "cake233/debian-lxde-armv7"

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
ldd = 'ldd (Debian GLIBC 2.36-7) 2.36'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
