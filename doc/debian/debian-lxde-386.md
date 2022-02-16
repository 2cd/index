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

## debian-lxde-386.toml

```toml
[main]
name = "debian"
tag = ["lxde", "2022-02-16"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
x11_or_wayland = true

[file]
name = "debian-lxde_i386_2022-02-16_13-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "68b7b5c44742e59f4448818cf68d3d68a26bf944753b70f72c2a063c1e0caca3"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.3G"
tar_bytes = 3471107072

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "978M"
zstd_bytes = 1024729669

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220209"
previous_tag = "2022-02-09"
previous_file = "debian-lxde_i386_2022-02-09_13-09-rootfs.tar.zst"
previous_sha256 = "67055e885f855274f332b3d9525ad5ea3795d07ed51f3073fd9d5a8968047c07"

current_version = "latest01"
current_date = "20220216"
old_file = "debian-lxde_i386_2022-02-02_13-14-rootfs.tar.zst"
old_sha256 = "172597c40a45a842e4cd6a8482ef3150fbd4f27a0d051280fe45c2e18bbb77e8"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-lxde_i386_2022-02-16_13-05-rootfs.tar.zst
# SHA256SUM=68b7b5c44742e59f4448818cf68d3d68a26bf944753b70f72c2a063c1e0caca3
# BUILD_DATE=20220216
# BUILD_TAG=2022-02-16
# STATUS=completed
# VERSION=latest01
# END_TIME=13:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-16
begin = 2022-02-16 12:23:35.848275656+00:00
start-sync_0 = 12:52:29
start-zstd = 12:55:15
start-sync_1 = 13:04:28
end-sync_1 = 13:05:30
end = 2022-02-16 13:05:30.185567248+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.8.1 (i686-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
