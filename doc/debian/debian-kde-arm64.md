# debian-kde-arm64

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
    --name debian-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-kde-arm64 zsh
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

## debian-kde-arm64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2022-08-03"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_arm64_2022-08-03_13-36.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1070ec0a5b5d8c2729436b08bfad9644c5764f0cfe41e79808b66d3d00f8a5db"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.9G"
tar_bytes = 6319033856

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1815178022

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220713"
previous_tag = "2022-07-13"
previous_file = "debian-kde_arm64_2022-07-13_13-31-rootfs.tar.zst"
previous_sha256 = "bb4767c4855b62e588048cd85088cae54c72cad5b70540bb5ac8ca0788b29aa8"

current_version = "latest01"
current_date = "20220803"
old_file = "debian-kde_arm64_2022-07-06_13-32-rootfs.tar.zst"
old_sha256 = "184a4caf05597ef541d46901a41d884eb440542d0e01498a1321630a88cb975b"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2022-08-03_13-36-rootfs.tar.zst
# SHA256SUM=1070ec0a5b5d8c2729436b08bfad9644c5764f0cfe41e79808b66d3d00f8a5db
# BUILD_DATE=20220803
# BUILD_TAG=2022-08-03
# STATUS=completed
# VERSION=latest01
# END_TIME=13:36

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-03
begin = 2022-08-03 12:23:20.148272050+00:00
start-sync_0 = 13:05:26
start-zstd = 13:11:10
start-sync_1 = 13:34:28
end-sync_1 = 13:36:14
end = 2022-08-03 13:36:14.883327327+00:00

[server]
repo = "cake233/debian-kde-arm64"

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
ldd = 'ldd (Debian GLIBC 2.33-8) 2.33'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
