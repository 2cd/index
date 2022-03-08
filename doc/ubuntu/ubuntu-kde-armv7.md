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
tag = ["kde", "2022-03-08", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "ubuntu-kde_armhf_2022-03-08_01-12.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "c932bb5ec7c5fecfa7e14550940707e589d21d394e2f54acf9769ce567df63c1"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.9G"
tar_bytes = 3067940352

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "951M"
zstd_bytes = 996532342

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220301"
previous_tag = "2022-03-01"
previous_file = "ubuntu-kde_armhf_2022-03-01_01-21-rootfs.tar.zst"
previous_sha256 = "883399af82f4f23ea6da8519e7c46a4546f894ddcf61637b51363d34662bbb9f"

current_version = "latest01"
current_date = "20220308"
old_file = "ubuntu-kde_armhf_2022-02-22_01-05-rootfs.tar.zst"
old_sha256 = "50073ac60e73844bf9bbad139b8b19f8ecd6d1612168db718898b5d82fd11425"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-kde_armhf_2022-03-08_01-12-rootfs.tar.zst
# SHA256SUM=c932bb5ec7c5fecfa7e14550940707e589d21d394e2f54acf9769ce567df63c1
# BUILD_DATE=20220308
# BUILD_TAG=2022-03-08
# STATUS=completed
# VERSION=latest01
# END_TIME=01:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-08
begin = 2022-03-08 00:20:51.674602875+00:00
start-sync_0 = 01:00:18
start-zstd = 01:03:05
start-sync_1 = 01:11:35
end-sync_1 = 01:12:45
end = 2022-03-08 01:12:45.354364765+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu1) 2.35'
zsh = 'zsh 5.8.1 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
