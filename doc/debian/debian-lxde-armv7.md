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
tag = ["lxde", "2023-08-23"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_armhf_2023-08-23_12-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c56ab2cf27ad1e7ccb28e925fd0886df9879752ab89c7cf883c15803a6502a88"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3166099968

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "962M"
zstd_bytes = 1008263770

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230816"
previous_tag = "2023-08-16"
previous_file = "debian-lxde_armhf_2023-08-16_13-01-rootfs.tar.zst"
previous_sha256 = "7a654824bc5d4c5e45ab56b80218a1e9e82111d46bbc88e9232f3863e5de99b5"

current_version = "latest01"
current_date = "20230823"
old_file = "debian-lxde_armhf_2023-08-09_13-00-rootfs.tar.zst"
old_sha256 = "5dcf84b20a47a9b761ccebec063687a5b7e6a3e07956e10e1d20645515f432d5"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2023-08-23_12-59-rootfs.tar.zst
# SHA256SUM=c56ab2cf27ad1e7ccb28e925fd0886df9879752ab89c7cf883c15803a6502a88
# BUILD_DATE=20230823
# BUILD_TAG=2023-08-23
# STATUS=completed
# VERSION=latest01
# END_TIME=12:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-23
begin = 2023-08-23 12:22:18.942504093+00:00
start-sync_0 = 12:46:14
start-zstd = 12:48:21
start-sync_1 = 12:57:56
end-sync_1 = 12:59:11
end = 2023-08-23 12:59:11.841751732+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
