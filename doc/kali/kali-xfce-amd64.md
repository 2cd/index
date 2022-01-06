# kali-xfce-amd64

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
    --name kali-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-amd64 zsh
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

## kali-xfce-amd64.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2022-01-06"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "kali-xfce_amd64_2022-01-06_13-04.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "79b9ed52ac96d4328b99ef40e1a6a53c331f426175e26dd6620546829b3b3603"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.3G"
tar_bytes = 5610792448

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1584237439

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211230"
previous_tag = "2021-12-30"
previous_file = "kali-xfce_amd64_2021-12-30_12-57-rootfs.tar.zst"
previous_sha256 = "9637e4c567a36904ed648a7935cd20411bfdf97054268e210a7e0a74f286e01a"

current_version = "latest01"
current_date = "20220106"
old_file = "kali-xfce_amd64_2021-12-23_12-54-rootfs.tar.zst"
old_sha256 = "73ab632bdbbf06746634031cfd35aa76ed2403d1e2d4b5d0b97ca8eba56a96f5"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-xfce_amd64_2022-01-06_13-04-rootfs.tar.zst
# SHA256SUM=79b9ed52ac96d4328b99ef40e1a6a53c331f426175e26dd6620546829b3b3603
# BUILD_DATE=20220106
# BUILD_TAG=2022-01-06
# STATUS=completed
# VERSION=latest01
# END_TIME=13:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-06
begin = 2022-01-06 12:18:22.141200640+00:00
start-sync_0 = 12:37:03
start-zstd = 12:44:40
start-sync_1 = 13:02:33
end-sync_1 = 13:04:25
end = 2022-01-06 13:04:25.385223785+00:00

[server]
repo = "cake233/kali-xfce-amd64"

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
ldd = 'ldd (Debian GLIBC 2.33-1) 2.33'
zsh = 'zsh 5.8 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
