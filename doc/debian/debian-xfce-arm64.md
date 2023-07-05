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

## debian-xfce-arm64.toml

```toml
[main]
name = "debian"
tag = ["xfce", "2023-07-05"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_arm64_2023-07-05_13-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c7bc56491d87d3b3bf01e2146fd29ef3f68e2f5c363aa83a91d81d9f8cdda4ab"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.8G"
tar_bytes = 2909075968

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "777M"
zstd_bytes = 813849520

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230628"
previous_tag = "2023-06-28"
previous_file = "debian-xfce_arm64_2023-06-28_13-25-rootfs.tar.zst"
previous_sha256 = "00db0f8dcdcd0d0007f119ba2904138b2a34acf202cf769296a0ba1a667b9b09"

current_version = "latest02"
current_date = "20230705"
old_file = "debian-xfce_arm64_2023-06-21_13-26-rootfs.tar.zst"
old_sha256 = "bd1bb9cee6d0cc68939610bb20e12180fcdc93a276e3a43b65c742cb01f2f5ca"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-xfce_arm64_2023-07-05_13-04-rootfs.tar.zst
# SHA256SUM=c7bc56491d87d3b3bf01e2146fd29ef3f68e2f5c363aa83a91d81d9f8cdda4ab
# BUILD_DATE=20230705
# BUILD_TAG=2023-07-05
# STATUS=completed
# VERSION=latest02
# END_TIME=13:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-05
begin = 2023-07-05 12:19:05.039808459+00:00
start-sync_0 = 12:51:45
start-zstd = 12:53:38
start-sync_1 = 13:04:03
end-sync_1 = 13:04:53
end = 2023-07-05 13:04:53.698161245+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-3) 2.37'
zsh = ''

[port]
tcp = [5902, 36080]
```
