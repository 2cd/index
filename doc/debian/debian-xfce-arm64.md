# debian-xfce-arm64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
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
    --name debian-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-xfce-arm64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```sh
    startvnc
```

or

```sh
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

## debian-xfce-arm64.toml

```toml
[main]
name = "debian"
tag = ["xfce", "2022-01-19"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "debian-xfce_arm64_2022-01-19_13-13.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "50cf0461e06ccd1637c6bd6d812bcf222b043e11bd8e70062d578536831420e8"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4196073472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1165879260

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220119"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-xfce_arm64_2022-01-19_13-13-rootfs.tar.zst
# SHA256SUM=50cf0461e06ccd1637c6bd6d812bcf222b043e11bd8e70062d578536831420e8
# BUILD_DATE=20220119
# BUILD_TAG=2022-01-19
# STATUS=completed
# VERSION=latest01
# END_TIME=13:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-19
begin = 2022-01-19 12:23:09.546907088+00:00
start-sync_0 = 12:57:32
start-zstd = 13:00:50
start-sync_1 = 13:12:29
end-sync_1 = 13:13:39
end = 2022-01-19 13:13:39.784744821+00:00

[server]
repo = "cake233/debian-xfce-arm64"

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
ldd = 'ldd (Debian GLIBC 2.33-3) 2.33'
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
