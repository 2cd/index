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
tag = ["kde", "2023-08-02"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_arm64_2023-08-02_13-44.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ea347eeb610188d1b6af5d3cb40ab559ea65cbd0a85b5af87061cdd3c8099df8"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.5G"
tar_bytes = 6973120000

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.9G"
zstd_bytes = 1965256824

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230726"
previous_tag = "2023-07-26"
previous_file = "debian-kde_arm64_2023-07-26_13-35-rootfs.tar.zst"
previous_sha256 = "f6bb80424f10f2955562d96479a53a23e5fc0b31d2d58e32fcd83f2fe878b35d"

current_version = "latest02"
current_date = "20230802"
old_file = "debian-kde_arm64_2023-07-19_13-37-rootfs.tar.zst"
old_sha256 = "6af0a4cd00fb1aeb390058c10bc5bae0011d99199d22c896f4e5fed4eedce093"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2023-08-02_13-44-rootfs.tar.zst
# SHA256SUM=ea347eeb610188d1b6af5d3cb40ab559ea65cbd0a85b5af87061cdd3c8099df8
# BUILD_DATE=20230802
# BUILD_TAG=2023-08-02
# STATUS=completed
# VERSION=latest02
# END_TIME=13:44

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-02
begin = 2023-08-02 12:22:54.814042521+00:00
start-sync_0 = 13:07:59
start-zstd = 13:15:23
start-sync_1 = 13:41:31
end-sync_1 = 13:44:11
end = 2023-08-02 13:44:12.025569507+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-6) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
