# kali-xfce-arm64

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
    --name kali-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-arm64 zsh
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

## kali-xfce-arm64.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2022-03-10"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "kali-xfce_arm64_2022-03-10_13-15.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "a0c376784491ca3187ea161f6b9a0eed2da99ff1c7a7779f73b1caaadf2d8dfb"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.2G"
tar_bytes = 4452392960

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1250549772

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220303"
previous_tag = "2022-03-03"
previous_file = "kali-xfce_arm64_2022-03-03_14-36-rootfs.tar.zst"
previous_sha256 = "f6249f8e355df43d20c4aae82ca472697ab228be080d8fb345ae0d4767e25b6d"

current_version = "latest02"
current_date = "20220310"
old_file = "kali-xfce_arm64_2022-02-24_13-57-rootfs.tar.zst"
old_sha256 = "b0e3bbf3a702c9be2bada9d4a229deff641e48f2f6dc52805baa05956e6da027"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2022-03-10_13-15-rootfs.tar.zst
# SHA256SUM=a0c376784491ca3187ea161f6b9a0eed2da99ff1c7a7779f73b1caaadf2d8dfb
# BUILD_DATE=20220310
# BUILD_TAG=2022-03-10
# STATUS=completed
# VERSION=latest02
# END_TIME=13:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-10
begin = 2022-03-10 12:20:34.503730034+00:00
start-sync_0 = 12:59:21
start-zstd = 13:02:52
start-sync_1 = 13:14:04
end-sync_1 = 13:15:23
end = 2022-03-10 13:15:23.501496433+00:00

[server]
repo = "cake233/kali-xfce-arm64"

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
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
