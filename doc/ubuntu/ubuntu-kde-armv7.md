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

```sh
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
tag = ["kde", "2022-02-15", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "ubuntu-kde_armhf_2022-02-15_01-04.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "a4f83b1cedf3fdd100bc92737605e9c6ab38ebd7b466bc16558fdff7e6aabbb4"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3175988224

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "972M"
zstd_bytes = 1019051643

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220208"
previous_tag = "2022-02-08"
previous_file = "ubuntu-kde_armhf_2022-02-08_01-20-rootfs.tar.zst"
previous_sha256 = "94bd71356939fdbb07efb3f4335d55eb22fcc8c0a668240b29354637641bed98"

current_version = "latest02"
current_date = "20220215"
old_file = "ubuntu-kde_armhf_2022-02-01_01-25-rootfs.tar.zst"
old_sha256 = "ddd7f0c8bde4f7752ad8bfffd60e2e24a20ac4cb71425e3e15a48e8989910907"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-kde_armhf_2022-02-15_01-04-rootfs.tar.zst
# SHA256SUM=a4f83b1cedf3fdd100bc92737605e9c6ab38ebd7b466bc16558fdff7e6aabbb4
# BUILD_DATE=20220215
# BUILD_TAG=2022-02-15
# STATUS=completed
# VERSION=latest02
# END_TIME=01:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-15
begin = 2022-02-15 00:21:27.262811601+00:00
start-sync_0 = 00:53:39
start-zstd = 00:56:09
start-sync_1 = 01:03:30
end-sync_1 = 01:04:32
end = 2022-02-15 01:04:32.559001900+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.34-0ubuntu3) 2.34'
zsh = 'zsh 5.8.1 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
