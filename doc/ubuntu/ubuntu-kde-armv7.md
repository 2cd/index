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
tag = ["kde", "2023-04-18", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_armhf_2023-04-18_00-51.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d9bed4277aaee6963380cccc00ee3bc5d4e1e33118881e264b653ee7376af397"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 4042162176

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1230822282

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230411"
previous_tag = "2023-04-11"
previous_file = "ubuntu-kde_armhf_2023-04-11_00-51-rootfs.tar.zst"
previous_sha256 = "c5c9f2f86b6ca5aa13a3f79a9e6683ea48f4efaf41ee165c1d58044d510ae07a"

current_version = "latest01"
current_date = "20230418"
old_file = "ubuntu-kde_armhf_2023-04-04_01-02-rootfs.tar.zst"
old_sha256 = "739168600dc84cd73196d1e00aaef7921f44b9445d0be42f76b76b52a3045e9a"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-kde_armhf_2023-04-18_00-51-rootfs.tar.zst
# SHA256SUM=d9bed4277aaee6963380cccc00ee3bc5d4e1e33118881e264b653ee7376af397
# BUILD_DATE=20230418
# BUILD_TAG=2023-04-18
# STATUS=completed
# VERSION=latest01
# END_TIME=00:51

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-18
begin = 2023-04-18 00:02:57.181902018+00:00
start-sync_0 = 00:34:58
start-zstd = 00:38:17
start-sync_1 = 00:50:34
end-sync_1 = 00:51:40
end = 2023-04-18 00:51:40.941849206+00:00

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
