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
tag = ["lxde", "2021-12-08"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "debian-lxde_armhf_2021-12-08_12-57.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "f0c8058a93d48bbbc607fef98407df9ed97ce50303fbe3006710ba16e6316b6f"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.6G"
tar_bytes = 2747738112

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "876M"
zstd_bytes = 918083629

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211201"
last_tag = "2021-12-01"
last_file = "debian-lxde_armhf_2021-12-01_12-57-rootfs.tar.zst"
last_sha256 = ""

current_version = "latest02"
current_date = "20211208"
old_file = "debian-lxde-armv7_2021-11-28_22-12-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2021-12-08_12-57-rootfs.tar.zst
# SHA256SUM=f0c8058a93d48bbbc607fef98407df9ed97ce50303fbe3006710ba16e6316b6f
# BUILD_DATE=20211208
# BUILD_TAG=2021-12-08
# STATUS=completed
# VERSION=latest02
# END_TIME=12:57

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-08
begin = 2021-12-08 12:19:51.540915399+00:00
start-sync_0 = 12:48:07
start-zstd = 12:50:08
start-sync_1 = 12:56:15
end-sync_1 = 12:57:16
end = 2021-12-08 12:57:16.392769419+00:00

[server]
repo = "cake233/debian-lxde-armv7"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "azure"
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
