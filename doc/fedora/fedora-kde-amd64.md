# fedora-kde-amd64

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
    --name fedora-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-kde-amd64 zsh
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

## fedora-kde-amd64.toml

```toml
[main]
name = "fedora"
tag = ["kde", "2023-10-10"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_amd64_2023-10-10_13-21.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d75f8e2deea15acbd980336206982fc66a2c636c58e4faf65ec330ce0df8e956"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.2G"
tar_bytes = 5499930624

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1718784966

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231003"
previous_tag = "2023-10-03"
previous_file = "fedora-kde_amd64_2023-10-03_13-24-rootfs.tar.zst"
previous_sha256 = "9323a0cfffd0accc1efdbaee6d7e775741bd8c447c97370db7cf451ac4d94f81"

current_version = "latest02"
current_date = "20231010"
old_file = "fedora-kde_amd64_2023-09-26_13-27-rootfs.tar.zst"
old_sha256 = "978d3a3230712d8e903defe919fc7260c5d79c074be6d300c74f5794330b0831"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-kde_amd64_2023-10-10_13-21-rootfs.tar.zst
# SHA256SUM=d75f8e2deea15acbd980336206982fc66a2c636c58e4faf65ec330ce0df8e956
# BUILD_DATE=20231010
# BUILD_TAG=2023-10-10
# STATUS=completed
# VERSION=latest02
# END_TIME=13:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-10
begin = 2023-10-10 12:47:50.746513416+00:00
start-sync_0 = 12:54:05
start-zstd = 12:58:18
start-sync_1 = 13:19:24
end-sync_1 = 13:21:16
end = 2023-10-10 13:21:16.080691385+00:00

[server]
repo = "cake233/fedora-kde-amd64"

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
ldd = 'ldd (GNU libc) 2.38.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
