# debian-xfce-amd64

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
    --name debian-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-xfce-amd64 zsh
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

## debian-xfce-amd64.toml

```toml
[main]
name = "debian"
tag = ["xfce", "2022-01-26"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "debian-xfce_amd64_2022-01-26_12-43.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "d429f29d9ea13591bd404911cc5096b8bd18701d69782cf569404951483aed27"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.4G"
tar_bytes = 3639920128

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "990M"
zstd_bytes = 1037739923

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220119"
previous_tag = "2022-01-19"
previous_file = "debian-xfce_amd64_2022-01-19_12-43-rootfs.tar.zst"
previous_sha256 = "297573284385e4d2dbd10970077f3a87f8f689cce601c30d06d212f855eef6dc"

current_version = "latest02"
current_date = "20220126"
old_file = "debian-xfce_amd64_2022-01-05_12-41-rootfs.tar.zst"
old_sha256 = "d068187ab82f3b48666ed61d0df7e4b6f5b5036086b4e7f6de045aaca6fa862f"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-xfce_amd64_2022-01-26_12-43-rootfs.tar.zst
# SHA256SUM=d429f29d9ea13591bd404911cc5096b8bd18701d69782cf569404951483aed27
# BUILD_DATE=20220126
# BUILD_TAG=2022-01-26
# STATUS=completed
# VERSION=latest02
# END_TIME=12:43

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-26
begin = 2022-01-26 12:21:16.557126674+00:00
start-sync_0 = 12:27:56
start-zstd = 12:31:42
start-sync_1 = 12:42:41
end-sync_1 = 12:43:57
end = 2022-01-26 12:43:57.318051809+00:00

[server]
repo = "cake233/debian-xfce-amd64"

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
ldd = 'ldd (Debian GLIBC 2.33-4) 2.33'
zsh = 'zsh 5.8 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
