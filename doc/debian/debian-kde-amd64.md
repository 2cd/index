# debian-kde-amd64

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
    --name debian-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-kde-amd64 zsh
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

## debian-kde-amd64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2023-04-05"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_amd64_2023-04-05_13-02.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "378fef0a7c8d6d91f21eab05e3d9d4c757586738ee09f9b8596cdad49f5fea1d"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.5G"
tar_bytes = 5813805568

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1690736798

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230329"
previous_tag = "2023-03-29"
previous_file = "debian-kde_amd64_2023-03-29_12-57-rootfs.tar.zst"
previous_sha256 = "454d3bfe72b0da4ef859b3909f97318342e5e853ef8dbc52804e4ab84cb765fb"

current_version = "latest01"
current_date = "20230405"
old_file = "debian-kde_amd64_2023-03-22_13-01-rootfs.tar.zst"
old_sha256 = "c05341db03f4423546a930fd71c7af8790f6783a72935170006b63b2407ea446"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-kde_amd64_2023-04-05_13-02-rootfs.tar.zst
# SHA256SUM=378fef0a7c8d6d91f21eab05e3d9d4c757586738ee09f9b8596cdad49f5fea1d
# BUILD_DATE=20230405
# BUILD_TAG=2023-04-05
# STATUS=completed
# VERSION=latest01
# END_TIME=13:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-05
begin = 2023-04-05 12:21:57.721870677+00:00
start-sync_0 = 12:30:21
start-zstd = 12:36:34
start-sync_1 = 13:00:31
end-sync_1 = 13:02:22
end = 2023-04-05 13:02:22.428650635+00:00

[server]
repo = "cake233/debian-kde-amd64"

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
