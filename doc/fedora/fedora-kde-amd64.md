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
tag = ["kde", "2023-10-24"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_amd64_2023-10-24_13-25.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d014e2a5991ca1aaae4108123b110b5c1bf2c348818deed10fcd5e1faf746d0a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.3G"
tar_bytes = 5652737024

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1754876846

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231017"
previous_tag = "2023-10-17"
previous_file = "fedora-kde_amd64_2023-10-17_13-36-rootfs.tar.zst"
previous_sha256 = "77ac6bf4d664aa30a5f3e1571aa4458fbeb15281cc30bff084b1ba736df9f500"

current_version = "latest02"
current_date = "20231024"
old_file = "fedora-kde_amd64_2023-10-10_13-21-rootfs.tar.zst"
old_sha256 = "d75f8e2deea15acbd980336206982fc66a2c636c58e4faf65ec330ce0df8e956"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-kde_amd64_2023-10-24_13-25-rootfs.tar.zst
# SHA256SUM=d014e2a5991ca1aaae4108123b110b5c1bf2c348818deed10fcd5e1faf746d0a
# BUILD_DATE=20231024
# BUILD_TAG=2023-10-24
# STATUS=completed
# VERSION=latest02
# END_TIME=13:25

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-24
begin = 2023-10-24 12:51:57.643550191+00:00
start-sync_0 = 12:59:04
start-zstd = 13:03:44
start-sync_1 = 13:23:27
end-sync_1 = 13:25:53
end = 2023-10-24 13:25:53.394419797+00:00

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
