# debian-lxde-armv7

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
    --name debian-lxde-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-lxde-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it debian-lxde-armv7 zsh
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

## debian-lxde-armv7.toml

```toml
[main]
name = "debian"
tag = ["lxde", "2021-12-01"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "debian-lxde_armhf_2021-12-01_12-57.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "598dee8f61cf7223c493c80ec9b6b083b75308fc6309b98e26fac845d2aca14b"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.6G"
tar_bytes = 2746349056

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "875M"
zstd_bytes = 917202686

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211128"
last_tag = "2021-11-28"
last_file = "debian-lxde-armv7_2021-11-28_22-12-rootfs.tar.zst"

current_version = "latest01"
current_date = "20211201"
old_file = "debian-sid_armhf+lxde-2021_11-03-rootfs.tar.zst"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2021-12-01_12-57-rootfs.tar.zst
# BUILD_DATE=20211201
# BUILD_TAG=2021-12-01
# STATUS=completed
# VERSION=latest01
# END_TIME=12:57

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-01
begin = 2021-12-01 12:18:04.641494582+00:00
start-sync_0 = 12:48:02
start-zstd = 12:50:04
start-sync_1 = 12:56:16
end-sync_1 = 12:57:18
end = 2021-12-01 12:57:18.146909372+00:00

[server]
repo = "cake233/debian-lxde-armv7"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "us"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "global"
current = false
last = true
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
