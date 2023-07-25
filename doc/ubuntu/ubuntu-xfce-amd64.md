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
tag = ["xfce", "2023-07-25", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_amd64_2023-07-25_00-30.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4a00ea97c6e7646128da2bdad6b468759355c19ad09f3b7b81f2d8ef65b92552"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.4G"
tar_bytes = 3640662016

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "947M"
zstd_bytes = 992825808

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230718"
previous_tag = "2023-07-18"
previous_file = "ubuntu-xfce_amd64_2023-07-18_00-26-rootfs.tar.zst"
previous_sha256 = "f6a985fb61b45be26468b85886b689b704460ccb2e9df8626425a9bd5a778e45"

current_version = "latest01"
current_date = "20230725"
old_file = "ubuntu-xfce_amd64_2023-07-11_00-31-rootfs.tar.zst"
old_sha256 = "0cb10d6dc8f7b35b4103ae5bc9d84738a53070cf855aeb983555d7fb6f54e4a9"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-xfce_amd64_2023-07-25_00-30-rootfs.tar.zst
# SHA256SUM=4a00ea97c6e7646128da2bdad6b468759355c19ad09f3b7b81f2d8ef65b92552
# BUILD_DATE=20230725
# BUILD_TAG=2023-07-25
# STATUS=completed
# VERSION=latest01
# END_TIME=00:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-25
begin = 2023-07-25 00:03:01.395000692+00:00
start-sync_0 = 00:10:02
start-zstd = 00:13:46
start-sync_1 = 00:28:57
end-sync_1 = 00:30:07
end = 2023-07-25 00:30:07.966625738+00:00

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
