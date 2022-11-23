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
tag = ["lxde", "2022-11-23"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_i386_2022-11-23_13-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d26df10625da12c31fb265b19f4c6cc17ae4cf8e3f40460b8f0326fec6911d81"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4335627776

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1219805061

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221116"
previous_tag = "2022-11-16"
previous_file = "debian-lxde_i386_2022-11-16_13-13-rootfs.tar.zst"
previous_sha256 = "0f991cea5de968de8ff8e084973b89aa3213d3ec85bb22c0869963f42af50142"

current_version = "latest02"
current_date = "20221123"
old_file = "debian-lxde_i386_2022-11-09_13-11-rootfs.tar.zst"
old_sha256 = "bd4d1fb6df478a4e28f4321f52db9a6d7cb2339b8dc9913e6b6e181efc3cc59d"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-lxde_i386_2022-11-23_13-20-rootfs.tar.zst
# SHA256SUM=d26df10625da12c31fb265b19f4c6cc17ae4cf8e3f40460b8f0326fec6911d81
# BUILD_DATE=20221123
# BUILD_TAG=2022-11-23
# STATUS=completed
# VERSION=latest02
# END_TIME=13:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-23
begin = 2022-11-23 12:18:44.624963544+00:00
start-sync_0 = 12:57:10
start-zstd = 13:01:25
start-sync_1 = 13:19:01
end-sync_1 = 13:20:28
end = 2022-11-23 13:20:28.141031403+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-5) 2.36'
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
