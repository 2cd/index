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
tag = ["lxde", "2023-04-19"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_armhf_2023-04-19_13-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c6e0916cd3781c3b2253b84431fa3a4575e67065d76ebfaf02aa7d7375991c94"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3128561152

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "947M"
zstd_bytes = 992803597

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230412"
previous_tag = "2023-04-12"
previous_file = "debian-lxde_armhf_2023-04-12_12-57-rootfs.tar.zst"
previous_sha256 = "85534b35c5cabcbefcdfeb02cbdee4d32e4ec00db6c8aea64d1495fff3ae0048"

current_version = "latest02"
current_date = "20230419"
old_file = "debian-lxde_armhf_2023-04-05_13-08-rootfs.tar.zst"
old_sha256 = "dc1354309e0071b7f577e7b807175fa56ca4a87c0ddabf6427903db3dac3972f"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2023-04-19_13-04-rootfs.tar.zst
# SHA256SUM=c6e0916cd3781c3b2253b84431fa3a4575e67065d76ebfaf02aa7d7375991c94
# BUILD_DATE=20230419
# BUILD_TAG=2023-04-19
# STATUS=completed
# VERSION=latest02
# END_TIME=13:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-19
begin = 2023-04-19 12:21:48.395818007+00:00
start-sync_0 = 12:51:06
start-zstd = 12:53:34
start-sync_1 = 13:03:51
end-sync_1 = 13:04:57
end = 2023-04-19 13:04:57.194935894+00:00

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
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
