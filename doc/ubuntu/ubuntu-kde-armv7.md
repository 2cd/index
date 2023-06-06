# ubuntu-kde-armv7

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
    --name ubuntu-kde-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-armv7 zsh
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

## ubuntu-kde-armv7.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2023-06-06", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_armhf_2023-06-06_00-52.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "94b8ebbb15b7f9fca20e7c4070eddfba47d89927840c357a2c05f304894afb2d"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 4046373888

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1231837668

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230530"
previous_tag = "2023-05-30"
previous_file = "ubuntu-kde_armhf_2023-05-30_00-51-rootfs.tar.zst"
previous_sha256 = "a6a6977c633964ad8eb226364d53c6f565b13386593f431caf4dd83bb5e12246"

current_version = "latest02"
current_date = "20230606"
old_file = "ubuntu-kde_armhf_2023-05-23_00-53-rootfs.tar.zst"
old_sha256 = "61d30d1a4a9226080c84d7256039c94c5d5ea3b1b52f07e0766acab6b4da07de"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-kde_armhf_2023-06-06_00-52-rootfs.tar.zst
# SHA256SUM=94b8ebbb15b7f9fca20e7c4070eddfba47d89927840c357a2c05f304894afb2d
# BUILD_DATE=20230606
# BUILD_TAG=2023-06-06
# STATUS=completed
# VERSION=latest02
# END_TIME=00:52

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-06
begin = 2023-06-06 00:03:02.304858592+00:00
start-sync_0 = 00:35:22
start-zstd = 00:38:21
start-sync_1 = 00:51:02
end-sync_1 = 00:52:12
end = 2023-06-06 00:52:13.039131224+00:00

[server]
repo = "cake233/ubuntu-kde-armv7"

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
