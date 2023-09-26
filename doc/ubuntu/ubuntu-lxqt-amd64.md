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
tag = ["lxqt", "2023-09-26", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_amd64_2023-09-26_01-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "11cf1f8b37bedce79cb1bbb9ceed047674da0fd59fde201c025acd277eb92f37"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4296248832

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1162045362

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230919"
previous_tag = "2023-09-19"
previous_file = "ubuntu-lxqt_amd64_2023-09-19_01-03-rootfs.tar.zst"
previous_sha256 = "d435f2766088060a07f0a0ef4aee11f4c274af5c354f66c3f18376c7425e1142"

current_version = "latest02"
current_date = "20230926"
old_file = "ubuntu-lxqt_amd64_2023-09-12_00-53-rootfs.tar.zst"
old_sha256 = "4c6ca6ae1d8a52311a3826e9b0ccacc0d16f19d31dd1b433256b32712b22425c"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-lxqt_amd64_2023-09-26_01-00-rootfs.tar.zst
# SHA256SUM=11cf1f8b37bedce79cb1bbb9ceed047674da0fd59fde201c025acd277eb92f37
# BUILD_DATE=20230926
# BUILD_TAG=2023-09-26
# STATUS=completed
# VERSION=latest02
# END_TIME=01:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-26
begin = 2023-09-26 00:26:10.889088582+00:00
start-sync_0 = 00:34:14
start-zstd = 00:39:25
start-sync_1 = 00:58:53
end-sync_1 = 01:00:36
end = 2023-09-26 01:00:36.314486602+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu4) 2.38'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
