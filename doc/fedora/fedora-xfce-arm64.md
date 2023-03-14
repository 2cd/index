# fedora-xfce-arm64

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
    --name fedora-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-xfce-arm64 zsh
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

## fedora-xfce-arm64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2023-03-14"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_arm64_2023-03-14_14-45.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5a54ad3717704dd2820dca17d52c484982080948920f0525ca00474f34301b6c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.5G"
tar_bytes = 5798384128

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1490235920

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230307"
previous_tag = "2023-03-07"
previous_file = "fedora-xfce_arm64_2023-03-07_15-10-rootfs.tar.zst"
previous_sha256 = "1e2ddb68a18aee806cc080e45d33e3f5dbc2d16610a3940b16356ffa372fd453"

current_version = "latest02"
current_date = "20230314"
old_file = "fedora-xfce_arm64_2023-02-28_15-37-rootfs.tar.zst"
old_sha256 = "0234861a8516b1a08898635fe738cdf8431ab04eacfc8e2be73bd3fc7e11d94d"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-xfce_arm64_2023-03-14_14-45-rootfs.tar.zst
# SHA256SUM=5a54ad3717704dd2820dca17d52c484982080948920f0525ca00474f34301b6c
# BUILD_DATE=20230314
# BUILD_TAG=2023-03-14
# STATUS=completed
# VERSION=latest02
# END_TIME=14:45

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-14
begin = 2023-03-14 13:02:42.797580715+00:00
start-sync_0 = 14:23:31
start-zstd = 14:27:41
start-sync_1 = 14:44:22
end-sync_1 = 14:45:52
end = 2023-03-14 14:45:52.784936087+00:00

[server]
repo = "cake233/fedora-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.37.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
