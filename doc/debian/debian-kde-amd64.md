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
tag = ["kde", "2023-10-25"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_amd64_2023-10-25_13-30.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f93f3a014195d89f881f0187e28c577e99358ca9560b946bc32805a7a598c74b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.6G"
tar_bytes = 5958184448

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1717741852

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231018"
previous_tag = "2023-10-18"
previous_file = "debian-kde_amd64_2023-10-18_13-36-rootfs.tar.zst"
previous_sha256 = "c38f77585c6aca050c56f57503f34e700c4a7d88be0bba8e3a4405d03b4b626f"

current_version = "latest01"
current_date = "20231025"
old_file = "debian-kde_amd64_2023-10-11_13-16-rootfs.tar.zst"
old_sha256 = "aa7163f38e2a3f01731838e2a109aa5834938a9812b416096be3f3b8573dc054"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-kde_amd64_2023-10-25_13-30-rootfs.tar.zst
# SHA256SUM=f93f3a014195d89f881f0187e28c577e99358ca9560b946bc32805a7a598c74b
# BUILD_DATE=20231025
# BUILD_TAG=2023-10-25
# STATUS=completed
# VERSION=latest01
# END_TIME=13:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-25
begin = 2023-10-25 12:46:34.453228471+00:00
start-sync_0 = 12:54:57
start-zstd = 13:01:17
start-sync_1 = 13:28:06
end-sync_1 = 13:30:12
end = 2023-10-25 13:30:12.996060509+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
