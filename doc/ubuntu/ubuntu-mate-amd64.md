# ubuntu-mate-amd64

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
    --name ubuntu-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-mate-amd64 zsh
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

## ubuntu-mate-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["mate", "2022-04-27", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-mate_amd64_2022-04-27_13-58.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5b6f54c6a1119d42e3590597693fd254737dbe449bf33eb09c40940c4bb385b8"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3783587840

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "967M"
zstd_bytes = 1013567796

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220426"
previous_tag = "2022-04-26"
previous_file = "ubuntu-mate_amd64_2022-04-26_00-47-rootfs.tar.zst"
previous_sha256 = "24421f9076d3c20a1c8c1694c3c4b82dd7d1a63432f67b8da1b0f2ddc1bc6af6"

current_version = "latest02"
current_date = "20220427"
old_file = "ubuntu-mate_amd64_2022-04-19_01-02-rootfs.tar.zst"
old_sha256 = "05ff8c13228925c7e9f3addbec01659b2d0c7a10bb13b72468cc7625f5b9ab57"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-mate_amd64_2022-04-27_13-58-rootfs.tar.zst
# SHA256SUM=5b6f54c6a1119d42e3590597693fd254737dbe449bf33eb09c40940c4bb385b8
# BUILD_DATE=20220427
# BUILD_TAG=2022-04-27
# STATUS=completed
# VERSION=latest02
# END_TIME=13:58

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-27
begin = 2022-04-27 13:34:36.206360283+00:00
start-sync_0 = 13:39:58
start-zstd = 13:43:49
start-sync_1 = 13:57:24
end-sync_1 = 13:58:32
end = 2022-04-27 13:58:33.002313939+00:00

[server]
repo = "cake233/ubuntu-mate-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.8.1 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
