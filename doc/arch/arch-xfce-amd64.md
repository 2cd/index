# arch-xfce-amd64

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
    --name arch-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-amd64 zsh
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

## arch-xfce-amd64.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2022-01-05"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "arch-xfce_amd64_2022-01-05_00-40.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "14a4f6d37f141df7cd1b58f6452e713a5884fd0aff47f94d98c34726e94a1a02"

# zstd: [1-22]
zstd-level = 15

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3851074560

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1268551872

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211229"
previous_tag = "2021-12-29"
previous_file = "arch-xfce_amd64_2021-12-29_00-41-rootfs.tar.zst"
previous_sha256 = "9c32e44f2d1427e1b047e5160ee59e60ddb54ba2fee874866e81ef1311a8883a"

current_version = "latest02"
current_date = "20220105"
old_file = "arch-xfce_amd64_2021-12-22_00-37-rootfs.tar.zst"
old_sha256 = "8d097033738eef711d96e02a54f351cb2edac21e23e4b73b6903a52d793fd09c"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-xfce_amd64_2022-01-05_00-40-rootfs.tar.zst
# SHA256SUM=14a4f6d37f141df7cd1b58f6452e713a5884fd0aff47f94d98c34726e94a1a02
# BUILD_DATE=20220105
# BUILD_TAG=2022-01-05
# STATUS=completed
# VERSION=latest02
# END_TIME=00:40

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-05
begin = 2022-01-05 00:21:49.196407188+00:00
start-sync_0 = 00:30:29
start-zstd = 00:34:11
start-sync_1 = 00:38:47
end-sync_1 = 00:40:07
end = 2022-01-05 00:40:07.376889032+00:00

[server]
repo = "cake233/arch-xfce-amd64"

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
ldd = 'ldd (GNU libc) 2.33'
zsh = 'zsh 5.8 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
