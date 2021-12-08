# fedora-mate-armv7

## How to run it?

```shell
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not armv7, then install qemu & binfmt-support.
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
    --name fedora-mate-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it fedora-mate-armv7 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```shell
    startvnc
```

or

```shell
    startx11vnc
```

or

```shell
    novnc
```

Note:

If you want to use novnc, then open your browser, and type the address:

```
localhost:36081
```

If you want to use tiger/x11vnc, then open vnc viewer, then type the address:

```
localhost:5903
```

## fedora-mate-armv7.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2021-12-07"]
os = "fedora"
release = "rawhide"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "fedora-mate_armhf_2021-12-07_13-18.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "2e006dbb873d6c6897fc54f6bfec426deb00d1dc91a683901f9e378965476247"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.2G"
tar_bytes = 3385818112

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1115930541

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211130"
previous_tag = "2021-11-30"
previous_file = "fedora-mate_armhf_2021-11-30_16-10-rootfs.tar.zst"
previous_sha256 = ""

current_version = "latest01"
current_date = "20211207"
old_file = "fedora-mate-armv7_2021-11-28_22-43-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=fedora-rawhide_armhf
# ROOTFS_FILE=fedora-mate_armhf_2021-12-07_13-18-rootfs.tar.zst
# SHA256SUM=2e006dbb873d6c6897fc54f6bfec426deb00d1dc91a683901f9e378965476247
# BUILD_DATE=20211207
# BUILD_TAG=2021-12-07
# STATUS=completed
# VERSION=latest01
# END_TIME=13:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-07
begin = 2021-12-07 12:39:54.314434898+00:00
start-sync_0 = 13:04:47
start-zstd = 13:07:50
start-sync_1 = 13:17:15
end-sync_1 = 13:18:36
end = 2021-12-07 13:18:36.047450255+00:00

[server]
repo = "cake233/fedora-mate-armv7"

[server.node1]
name = "cn"
current = false
previous = true
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
zsh = 'zsh 5.8 (armv7hl-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
