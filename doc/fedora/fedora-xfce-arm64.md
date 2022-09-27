# fedora-xfce-arm64

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
    --name fedora-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-xfce-arm64 zsh
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

## fedora-xfce-arm64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2022-09-27"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_arm64_2022-09-27_14-48.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4962519f549ef842351b0a4d08fd1429ce97e10553f75eb47fa606bd86bf49bd"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.5G"
tar_bytes = 5834625536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1632459719

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220920"
previous_tag = "2022-09-20"
previous_file = "fedora-xfce_arm64_2022-09-20_14-31-rootfs.tar.zst"
previous_sha256 = "4b4f74bb907d783b8f176871471c6ad2e276e0d241e9c3525dc79e367c29bffe"

current_version = "latest02"
current_date = "20220927"
old_file = "fedora-xfce_arm64_2022-09-13_14-24-rootfs.tar.zst"
old_sha256 = "9968091d6a4c081c76bb713ca6b626ced79bb303362b9585ae5a22a50154bce9"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-xfce_arm64_2022-09-27_14-48-rootfs.tar.zst
# SHA256SUM=4962519f549ef842351b0a4d08fd1429ce97e10553f75eb47fa606bd86bf49bd
# BUILD_DATE=20220927
# BUILD_TAG=2022-09-27
# STATUS=completed
# VERSION=latest02
# END_TIME=14:48

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-27
begin = 2022-09-27 12:49:04.808274712+00:00
start-sync_0 = 14:18:00
start-zstd = 14:23:44
start-sync_1 = 14:46:16
end-sync_1 = 14:48:05
end = 2022-09-27 14:48:05.438375091+00:00

[server]
repo = "cake233/fedora-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
