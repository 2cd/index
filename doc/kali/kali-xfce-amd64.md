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

## kali-xfce-amd64.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2023-08-24"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_amd64_2023-08-24_13-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ae9b7e8044ca74ee877a723bbd28fbb368d8e517cc0ea3ce29ca141e4f8616a6"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4843044352

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1375753182

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230817"
previous_tag = "2023-08-17"
previous_file = "kali-xfce_amd64_2023-08-17_13-05-rootfs.tar.zst"
previous_sha256 = "e7d2150fcebcfe7b2128831941e458622e397e1749d83c13873a64225c05fd76"

current_version = "latest02"
current_date = "20230824"
old_file = "kali-xfce_amd64_2023-08-10_13-06-rootfs.tar.zst"
old_sha256 = "3fcf5f48cbb0676d78cd8945023b2cd7a03161253beb5d0fbbb174611c0fb7ef"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-xfce_amd64_2023-08-24_13-08-rootfs.tar.zst
# SHA256SUM=ae9b7e8044ca74ee877a723bbd28fbb368d8e517cc0ea3ce29ca141e4f8616a6
# BUILD_DATE=20230824
# BUILD_TAG=2023-08-24
# STATUS=completed
# VERSION=latest02
# END_TIME=13:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-24
begin = 2023-08-24 12:30:33.280608926+00:00
start-sync_0 = 12:39:59
start-zstd = 12:45:09
start-sync_1 = 13:06:59
end-sync_1 = 13:08:48
end = 2023-08-24 13:08:48.747874945+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-6) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
