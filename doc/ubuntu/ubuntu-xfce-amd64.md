# ubuntu-xfce-amd64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not amd64, then install qemu & binfmt-support.
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
    --name ubuntu-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-xfce-amd64 zsh
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

## ubuntu-xfce-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2022-12-20", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_amd64_2022-12-20_00-25.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2d28cab790e1f798602bc1797b6481644347abe176214a09c4d355641b6e8a73"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.5G"
tar_bytes = 3672592896

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "958M"
zstd_bytes = 1003996873

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221213"
previous_tag = "2022-12-13"
previous_file = "ubuntu-xfce_amd64_2022-12-13_00-24-rootfs.tar.zst"
previous_sha256 = "64f62effc347b4a36ce5af7805a931c2703f5c6e07409d512af8cacc818a98e0"

current_version = "latest01"
current_date = "20221220"
old_file = "ubuntu-xfce_amd64_2022-12-06_00-24-rootfs.tar.zst"
old_sha256 = "d9a9558518adf96e365cbdda64077ba631083d7f3908f6457985e1c1eb38603a"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-xfce_amd64_2022-12-20_00-25-rootfs.tar.zst
# SHA256SUM=2d28cab790e1f798602bc1797b6481644347abe176214a09c4d355641b6e8a73
# BUILD_DATE=20221220
# BUILD_TAG=2022-12-20
# STATUS=completed
# VERSION=latest01
# END_TIME=00:25

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-20
begin = 2022-12-20 00:03:18.200634358+00:00
start-sync_0 = 00:08:44
start-zstd = 00:11:47
start-sync_1 = 00:24:31
end-sync_1 = 00:25:28
end = 2022-12-20 00:25:28.106550705+00:00

[server]
repo = "cake233/ubuntu-xfce-amd64"

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
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
