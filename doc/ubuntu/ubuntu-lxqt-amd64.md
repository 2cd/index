# ubuntu-lxqt-amd64

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
    --name ubuntu-lxqt-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-lxqt-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-lxqt-amd64 zsh
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

## ubuntu-lxqt-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2023-11-14", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_amd64_2023-11-14_00-45.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "70f86e7484e03da758bbb8d5b3a285faa6bca57060849a5b70ba062b867413aa"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4308724224

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1165540953

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231107"
previous_tag = "2023-11-07"
previous_file = "ubuntu-lxqt_amd64_2023-11-07_00-46-rootfs.tar.zst"
previous_sha256 = "de2cb9c3b24e06a1487863392b87a120ce3eefe4e3ef02bac73450b9552c191c"

current_version = "latest02"
current_date = "20231114"
old_file = "ubuntu-lxqt_amd64_2023-10-24_00-57-rootfs.tar.zst"
old_sha256 = "e341db0a122996af0ece25e1e1556126c75ccddde8dc1bb4e1b229e203e47897"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-lxqt_amd64_2023-11-14_00-45-rootfs.tar.zst
# SHA256SUM=70f86e7484e03da758bbb8d5b3a285faa6bca57060849a5b70ba062b867413aa
# BUILD_DATE=20231114
# BUILD_TAG=2023-11-14
# STATUS=completed
# VERSION=latest02
# END_TIME=00:45

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-14
begin = 2023-11-14 00:23:15.592565848+00:00
start-sync_0 = 00:30:24
start-zstd = 00:32:55
start-sync_1 = 00:44:33
end-sync_1 = 00:45:38
end = 2023-11-14 00:45:38.191843000+00:00

[server]
repo = "cake233/ubuntu-lxqt-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu6) 2.38'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
