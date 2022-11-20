# arch-xfce-armv7

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
    --name arch-xfce-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-armv7 zsh
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

## arch-xfce-armv7.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2022-11-20"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_armhf_2022-11-20_19-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5756fe0f34e5c078c9c8d32d93b4d32e238062fbd6c6f256fe58a33b1699fb8f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.2G"
tar_bytes = 3396912640

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1124543452

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221116"
previous_tag = "2022-11-16"
previous_file = "arch-xfce_armhf_2022-11-16_00-37-rootfs.tar.zst"
previous_sha256 = "132cd3b5b6312b0d3b13301c7c72d361994a65050e58ca0bc172f3e9b9522e7b"

current_version = "latest02"
current_date = "20221120"
old_file = "arch-xfce_armhf_2022-11-09_01-49-rootfs.tar.zst"
old_sha256 = "aa02749dcb96b454800bf0309fe32bc684c4d3b12c9293f4e7b316c622323c2a"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-xfce_armhf_2022-11-20_19-04-rootfs.tar.zst
# SHA256SUM=5756fe0f34e5c078c9c8d32d93b4d32e238062fbd6c6f256fe58a33b1699fb8f
# BUILD_DATE=20221120
# BUILD_TAG=2022-11-20
# STATUS=completed
# VERSION=latest02
# END_TIME=19:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-20
begin = 2022-11-20 18:25:23.593375207+00:00
start-sync_0 = 18:46:42
start-zstd = 18:49:57
start-sync_1 = 19:03:43
end-sync_1 = 19:04:56
end = 2022-11-20 19:04:56.786078361+00:00

[server]
repo = "cake233/arch-xfce-armv7"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (armv7l-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
