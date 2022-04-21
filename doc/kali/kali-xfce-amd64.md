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
tag = ["xfce", "2022-04-21"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true
syntax_version = "0.0.0-alpha.3"

[file]
name = "kali-xfce_amd64_2022-04-21_13-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "26f0050f9f9778710c1421b4ac5c3eeb21fa5f69a5257544c9929fdee6b6f9e3"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.4G"
tar_bytes = 5718516736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1594509131

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220414"
previous_tag = "2022-04-14"
previous_file = "kali-xfce_amd64_2022-04-14_12-56-rootfs.tar.zst"
previous_sha256 = "ad1cfb4c9623f1eb76357fade402b217dde20d169a961747179bb0df527543c8"

current_version = "latest02"
current_date = "20220421"
old_file = "kali-xfce_amd64_2022-04-07_11-58-rootfs.tar.zst"
old_sha256 = "ba160c4606476e06051a3d5225ef87a04147856e0de6177a40573f8f986eeb02"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-xfce_amd64_2022-04-21_13-01-rootfs.tar.zst
# SHA256SUM=26f0050f9f9778710c1421b4ac5c3eeb21fa5f69a5257544c9929fdee6b6f9e3
# BUILD_DATE=20220421
# BUILD_TAG=2022-04-21
# STATUS=completed
# VERSION=latest02
# END_TIME=13:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-21
begin = 2022-04-21 12:23:50.241919696+00:00
start-sync_0 = 12:34:08
start-zstd = 12:40:18
start-sync_1 = 12:59:37
end-sync_1 = 13:01:13
end = 2022-04-21 13:01:13.766626521+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.8.1 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
