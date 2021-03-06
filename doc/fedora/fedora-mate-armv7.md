# fedora-mate-armv7

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
    --name fedora-mate-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-armv7 zsh
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

## fedora-mate-armv7.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2022-04-12"]
os = "fedora"
release = "rawhide"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true
syntax_version = "0.0.0-alpha.3"

[file]
name = "fedora-mate_armhf_2022-04-12_12-53.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3ac27eab69576c0ed9c2ff929209f3e8812ed3b14fb110ab5409948e45e16582"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "992M"
tar_bytes = 1039143936

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "192M"
zstd_bytes = 200743594

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220405"
previous_tag = "2022-04-05"
previous_file = "fedora-mate_armhf_2022-04-05_12-23-rootfs.tar.zst"
previous_sha256 = "4e40954d7c6cc088b1ce99ee8774fd80ebf15e3c5663abd1e6dc81f9ab4f15cf"

current_version = "latest01"
current_date = "20220412"
old_file = "fedora-mate_armhf_2022-03-29_12-43-rootfs.tar.zst"
old_sha256 = "f598cd5e33004d4ef2110f7c9eda991fc590eadf654def4712f5e110b6abd279"
# edition 2021
# DISTRO_NAME=fedora-rawhide_armhf
# ROOTFS_FILE=fedora-mate_armhf_2022-04-12_12-53-rootfs.tar.zst
# SHA256SUM=3ac27eab69576c0ed9c2ff929209f3e8812ed3b14fb110ab5409948e45e16582
# BUILD_DATE=20220412
# BUILD_TAG=2022-04-12
# STATUS=completed
# VERSION=latest01
# END_TIME=12:53

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-12
begin = 2022-04-12 12:44:34.660964418+00:00
start-sync_0 = 12:48:56
start-zstd = 12:49:53
start-sync_1 = 12:53:01
end-sync_1 = 12:53:17
end = 2022-04-12 12:53:17.510461740+00:00

[server]
repo = "cake233/fedora-mate-armv7"

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
ldd = 'ldd (GNU libc) 2.34.9000'
zsh = 'zsh 5.8 (armv7hl-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
