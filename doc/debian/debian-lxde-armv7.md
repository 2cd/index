# debian-lxde-armv7

## How to run it?

```sh
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

```sh
    docker exex -it debian-lxde-armv7 zsh
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

## debian-lxde-armv7.toml

```toml
[main]
name = "debian"
tag = ["lxde", "2022-03-23"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "debian-lxde_armhf_2022-03-23_13-00.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "7044ae40be66edcb12d56aff16c01d8203e55cfd661822fdb1b84ca15c9374d0"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.5G"
tar_bytes = 2670042112

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "861M"
zstd_bytes = 901993566

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220316"
previous_tag = "2022-03-16"
previous_file = "debian-lxde_armhf_2022-03-16_12-51-rootfs.tar.zst"
previous_sha256 = "e1883b5e686a118f15c2be7852d7c022fb6a08cccb016f18aabd813c0c9f3d7f"

current_version = "latest01"
current_date = "20220323"
old_file = "debian-lxde_armhf_2022-03-09_12-52-rootfs.tar.zst"
old_sha256 = "f77197b7aff022b22fe70b9f88e6a88b2bda528db3e32ec9772f44405251db85"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2022-03-23_13-00-rootfs.tar.zst
# SHA256SUM=7044ae40be66edcb12d56aff16c01d8203e55cfd661822fdb1b84ca15c9374d0
# BUILD_DATE=20220323
# BUILD_TAG=2022-03-23
# STATUS=completed
# VERSION=latest01
# END_TIME=13:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-23
begin = 2022-03-23 12:23:16.778020481+00:00
start-sync_0 = 12:50:08
start-zstd = 12:52:14
start-sync_1 = 12:59:06
end-sync_1 = 13:00:06
end = 2022-03-23 13:00:06.171538813+00:00

[server]
repo = "cake233/debian-lxde-armv7"

[server.node1]
name = "cn"
current = false
previous = false
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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.8.1 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
