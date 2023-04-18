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
tag = ["lxqt", "2023-04-18", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_amd64_2023-04-18_00-35.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2c2af29a0c4be1bdcfcb50b9d99b06798b620310f17b32b90ff79fee99b7460d"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3951889920

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1023M"
zstd_bytes = 1072581953

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230411"
previous_tag = "2023-04-11"
previous_file = "ubuntu-lxqt_amd64_2023-04-11_00-28-rootfs.tar.zst"
previous_sha256 = "9e5c1966b343a55e7c796cf89d4ef674ff8031bb82ad70782c662e9bd3a3c2ae"

current_version = "latest02"
current_date = "20230418"
old_file = "ubuntu-lxqt_amd64_2023-04-04_00-28-rootfs.tar.zst"
old_sha256 = "55fc8965d20a31aac2770e7172db7791a5c4362969ee722bfe43687d9b19e5c3"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-lxqt_amd64_2023-04-18_00-35-rootfs.tar.zst
# SHA256SUM=2c2af29a0c4be1bdcfcb50b9d99b06798b620310f17b32b90ff79fee99b7460d
# BUILD_DATE=20230418
# BUILD_TAG=2023-04-18
# STATUS=completed
# VERSION=latest02
# END_TIME=00:35

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-18
begin = 2023-04-18 00:03:00.929132454+00:00
start-sync_0 = 00:11:50
start-zstd = 00:15:54
start-sync_1 = 00:33:48
end-sync_1 = 00:35:00
end = 2023-04-18 00:35:00.122821238+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
