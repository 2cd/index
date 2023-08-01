# ubuntu-kde-amd64

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
    --name ubuntu-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-amd64 zsh
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

## ubuntu-kde-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2023-08-01", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_amd64_2023-08-01_00-38.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6a0ba962ca1c29daf06151b579d12f2cbbce6316d52926a4e4a169171d346812"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4765608960

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1322242411

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230725"
previous_tag = "2023-07-25"
previous_file = "ubuntu-kde_amd64_2023-07-25_00-33-rootfs.tar.zst"
previous_sha256 = "555e113713c593925b90585d2ec92912ab988a389a4f2511d39cb57f53ab0e54"

current_version = "latest02"
current_date = "20230801"
old_file = "ubuntu-kde_amd64_2023-07-18_00-38-rootfs.tar.zst"
old_sha256 = "d781249798927f877df5c1a3da8e67b31e844e23585bfea097b3bd32bca7c571"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kde_amd64_2023-08-01_00-38-rootfs.tar.zst
# SHA256SUM=6a0ba962ca1c29daf06151b579d12f2cbbce6316d52926a4e4a169171d346812
# BUILD_DATE=20230801
# BUILD_TAG=2023-08-01
# STATUS=completed
# VERSION=latest02
# END_TIME=00:38

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-01
begin = 2023-08-01 00:03:08.260737906+00:00
start-sync_0 = 00:12:02
start-zstd = 00:17:01
start-sync_1 = 00:37:13
end-sync_1 = 00:38:55
end = 2023-08-01 00:38:55.051741392+00:00

[server]
repo = "cake233/ubuntu-kde-amd64"

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
