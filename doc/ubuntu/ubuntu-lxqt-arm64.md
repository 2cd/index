# ubuntu-lxqt-arm64

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
    --name ubuntu-lxqt-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-lxqt-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-lxqt-arm64 zsh
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

## ubuntu-lxqt-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2023-01-17", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_arm64_2023-01-17_00-52.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4dba7d34b19429e965a12a7eec658013e35c5e71719a2407d9621e51ba42ecb7"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4245062656

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1149423067

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230110"
previous_tag = "2023-01-10"
previous_file = "ubuntu-lxqt_arm64_2023-01-10_01-04-rootfs.tar.zst"
previous_sha256 = "6dfcf0d8b40f150010a2ee516f39f3cff3034e2d47597977315f7dee0774d1ba"

current_version = "latest01"
current_date = "20230117"
old_file = "ubuntu-lxqt_arm64_2023-01-03_00-56-rootfs.tar.zst"
old_sha256 = "1c716dab7c070cf1030c3abecab931190340efb65cf8f2a70a3923050ba4bce9"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-lxqt_arm64_2023-01-17_00-52-rootfs.tar.zst
# SHA256SUM=4dba7d34b19429e965a12a7eec658013e35c5e71719a2407d9621e51ba42ecb7
# BUILD_DATE=20230117
# BUILD_TAG=2023-01-17
# STATUS=completed
# VERSION=latest01
# END_TIME=00:52

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-17
begin = 2023-01-17 00:02:59.753939690+00:00
start-sync_0 = 00:34:17
start-zstd = 00:37:29
start-sync_1 = 00:51:19
end-sync_1 = 00:52:26
end = 2023-01-17 00:52:26.767495840+00:00

[server]
repo = "cake233/ubuntu-lxqt-arm64"

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
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
