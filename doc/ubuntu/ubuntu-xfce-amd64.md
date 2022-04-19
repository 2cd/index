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
tag = ["xfce", "2022-04-19", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true
syntax_version = "0.0.0-alpha.3"

[file]
name = "ubuntu-xfce_amd64_2022-04-19_01-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5b87f4156b8bd927b4b56bb7c13c02d5d5d0c16df0c7333d31eb151630571fab"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3217335808

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "831M"
zstd_bytes = 870565856

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220411"
previous_tag = "2022-04-11"
previous_file = "ubuntu-xfce_amd64_2022-04-11_23-39-rootfs.tar.zst"
previous_sha256 = "d8564be5ebdb02a4cdf0974242d2d5ca042ed8b4a4c0fa89299d5fa450b642f6"

current_version = "latest02"
current_date = "20220419"
old_file = "ubuntu-xfce_amd64_2022-04-04_23-42-rootfs.tar.zst"
old_sha256 = "d42cc6be5c4856f587e77a805f3b914e7cc6f41fdbb65ca7e909996988af3ed0"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-xfce_amd64_2022-04-19_01-00-rootfs.tar.zst
# SHA256SUM=5b87f4156b8bd927b4b56bb7c13c02d5d5d0c16df0c7333d31eb151630571fab
# BUILD_DATE=20220419
# BUILD_TAG=2022-04-19
# STATUS=completed
# VERSION=latest02
# END_TIME=01:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-19
begin = 2022-04-19 00:40:28.515559560+00:00
start-sync_0 = 00:45:40
start-zstd = 00:48:14
start-sync_1 = 01:00:00
end-sync_1 = 01:00:57
end = 2022-04-19 01:00:57.561604953+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.8.1 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
