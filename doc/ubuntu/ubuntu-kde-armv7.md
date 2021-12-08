# ubuntu-kde-armv7

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
    --name ubuntu-kde-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it ubuntu-kde-armv7 zsh
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

## ubuntu-kde-armv7.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2021-12-07", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "ubuntu-kde_armhf_2021-12-07_02-17.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "9d9bdcfcdc399a2ad4298b3dcc5f25da742006d2f4c4de78db5058322629fbc1"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3171275776

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1015M"
zstd_bytes = 1063342262

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211130"
previous_tag = "2021-11-30"
previous_file = "ubuntu-kde_armhf_2021-11-30_15-19-rootfs.tar.zst"
previous_sha256 = ""

current_version = "latest01"
current_date = "20211207"
old_file = "ubuntu-kde-armv7_2021-11-28_22-35-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-kde_armhf_2021-12-07_02-17-rootfs.tar.zst
# SHA256SUM=9d9bdcfcdc399a2ad4298b3dcc5f25da742006d2f4c4de78db5058322629fbc1
# BUILD_DATE=20211207
# BUILD_TAG=2021-12-07
# STATUS=completed
# VERSION=latest01
# END_TIME=02:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-07
begin = 2021-12-07 00:23:06.866419955+00:00
start-sync_0 = 02:03:42
start-zstd = 02:06:39
start-sync_1 = 02:15:47
end-sync_1 = 02:17:04
end = 2021-12-07 02:17:04.967466993+00:00

[server]
repo = "cake233/ubuntu-kde-armv7"

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
zsh = 'zsh 5.8 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
