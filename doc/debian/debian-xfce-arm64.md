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
tag = ["xfce", "2023-10-04"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_arm64_2023-10-04_14-24.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "29157083d651fd89d7ef8b02c65936f742ce7364c51f2a3f7442cceb85ad6461"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4876468224

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1312886765

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230927"
previous_tag = "2023-09-27"
previous_file = "debian-xfce_arm64_2023-09-27_14-13-rootfs.tar.zst"
previous_sha256 = "50a430b327a0e35d7c2bb58f977cea2c3dc01b544c8ca45911d32b170b042221"

current_version = "latest02"
current_date = "20231004"
old_file = "debian-xfce_arm64_2023-09-20_14-14-rootfs.tar.zst"
old_sha256 = "6028dd9107628b9ffcf2198717aaacaf29665ccda3b2cb075af99ba373ee4a2a"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-xfce_arm64_2023-10-04_14-24-rootfs.tar.zst
# SHA256SUM=29157083d651fd89d7ef8b02c65936f742ce7364c51f2a3f7442cceb85ad6461
# BUILD_DATE=20231004
# BUILD_TAG=2023-10-04
# STATUS=completed
# VERSION=latest02
# END_TIME=14:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-04
begin = 2023-10-04 12:37:40.158662904+00:00
start-sync_0 = 14:02:01
start-zstd = 14:05:52
start-sync_1 = 14:22:47
end-sync_1 = 14:24:14
end = 2023-10-04 14:24:14.449930240+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
