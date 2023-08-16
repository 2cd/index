# debian-lxde-386

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not 386, then install qemu & binfmt-support.
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
    --name debian-lxde-386 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-lxde-386

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-lxde-386 zsh
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

## debian-lxde-386.toml

```toml
[main]
name = "debian"
tag = ["lxde", "2023-08-16"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_i386_2023-08-16_13-32.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5856f06738f31380a143543e02792103d087c96317c79739973417dd75664dae"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.2G"
tar_bytes = 4410074112

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1244164917

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230809"
previous_tag = "2023-08-09"
previous_file = "debian-lxde_i386_2023-08-09_13-36-rootfs.tar.zst"
previous_sha256 = "8d978da4486bab41d76dc1ad29f8bfe952b97764e66e850a944bad12ec0db8ff"

current_version = "latest02"
current_date = "20230816"
old_file = "debian-lxde_i386_2023-08-02_13-27-rootfs.tar.zst"
old_sha256 = "bac5767c6736d74c78fdc95a51ca2d8966cfc7a46a82c5c4bdab9ce117976dca"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-lxde_i386_2023-08-16_13-32-rootfs.tar.zst
# SHA256SUM=5856f06738f31380a143543e02792103d087c96317c79739973417dd75664dae
# BUILD_DATE=20230816
# BUILD_TAG=2023-08-16
# STATUS=completed
# VERSION=latest02
# END_TIME=13:32

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-16
begin = 2023-08-16 12:24:32.194629737+00:00
start-sync_0 = 13:05:28
start-zstd = 13:09:57
start-sync_1 = 13:30:18
end-sync_1 = 13:32:14
end = 2023-08-16 13:32:14.333753835+00:00

[server]
repo = "cake233/debian-lxde-386"

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
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
