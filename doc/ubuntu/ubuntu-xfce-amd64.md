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
tag = ["xfce", "2022-11-29", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_amd64_2022-11-29_00-25.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fbe0919442948277e8f1588f8d1a5c9c7a40e23c221bec393f80481604af4fa4"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.5G"
tar_bytes = 3661603840

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "956M"
zstd_bytes = 1002244597

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221122"
previous_tag = "2022-11-22"
previous_file = "ubuntu-xfce_amd64_2022-11-22_00-25-rootfs.tar.zst"
previous_sha256 = "e185dafbc99e5f869a5e55a669011c01770aca9bf4ac85f9c45b63fb5dc78d50"

current_version = "latest02"
current_date = "20221129"
old_file = "ubuntu-xfce_amd64_2022-11-15_00-23-rootfs.tar.zst"
old_sha256 = "84968ccd8959cfd39403c4728e47c99fb745f914e7904b41ae7e54b356580e60"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-xfce_amd64_2022-11-29_00-25-rootfs.tar.zst
# SHA256SUM=fbe0919442948277e8f1588f8d1a5c9c7a40e23c221bec393f80481604af4fa4
# BUILD_DATE=20221129
# BUILD_TAG=2022-11-29
# STATUS=completed
# VERSION=latest02
# END_TIME=00:25

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-29
begin = 2022-11-29 00:03:04.936238230+00:00
start-sync_0 = 00:08:37
start-zstd = 00:11:41
start-sync_1 = 00:24:45
end-sync_1 = 00:25:42
end = 2022-11-29 00:25:42.493092494+00:00

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
