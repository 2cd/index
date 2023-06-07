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
tag = ["xfce", "2023-06-07"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_arm64_2023-06-07_13-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ba2571afe2518e81a36a0f8a49dacbe7f165f2512d7e5f763b938bf37a46122f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4797523968

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1287434731

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230531"
previous_tag = "2023-05-31"
previous_file = "debian-xfce_arm64_2023-05-31_13-22-rootfs.tar.zst"
previous_sha256 = "8d91bd5d00974a6e1e4a8352d068eae7f4298668bbe11c86d8b3c6b79856d08c"

current_version = "latest02"
current_date = "20230607"
old_file = "debian-xfce_arm64_2023-05-24_13-24-rootfs.tar.zst"
old_sha256 = "cdee471cad9819e7344b58241ef9f807ae326a0288f8db37d6632031acfb597a"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-xfce_arm64_2023-06-07_13-18-rootfs.tar.zst
# SHA256SUM=ba2571afe2518e81a36a0f8a49dacbe7f165f2512d7e5f763b938bf37a46122f
# BUILD_DATE=20230607
# BUILD_TAG=2023-06-07
# STATUS=completed
# VERSION=latest02
# END_TIME=13:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-07
begin = 2023-06-07 12:24:55.856736729+00:00
start-sync_0 = 12:56:24
start-zstd = 13:00:03
start-sync_1 = 13:16:59
end-sync_1 = 13:18:15
end = 2023-06-07 13:18:15.040803648+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
