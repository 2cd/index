# ubuntu-mate-amd64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not amd64, then install qemu & binfmt-support.
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
    --name ubuntu-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-mate-amd64 zsh
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

## ubuntu-mate-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["mate", "2022-12-06", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-mate_amd64_2022-12-06_00-27.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ff09d99fe87d7e7c963e59a1df2229666e10fd40cc8c3c542a875cf0e5474248"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4329533952

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1159807860

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221129"
previous_tag = "2022-11-29"
previous_file = "ubuntu-mate_amd64_2022-11-29_00-32-rootfs.tar.zst"
previous_sha256 = "57500d5bd597d499ff0fe7825daa3753f44e46d4645553581a4a11b37761d099"

current_version = "latest01"
current_date = "20221206"
old_file = "ubuntu-mate_amd64_2022-11-22_00-29-rootfs.tar.zst"
old_sha256 = "ad935a6f968971b5724a25c7a2265143497d1a82990e5052329b3b0f39e3e4d3"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-mate_amd64_2022-12-06_00-27-rootfs.tar.zst
# SHA256SUM=ff09d99fe87d7e7c963e59a1df2229666e10fd40cc8c3c542a875cf0e5474248
# BUILD_DATE=20221206
# BUILD_TAG=2022-12-06
# STATUS=completed
# VERSION=latest01
# END_TIME=00:27

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-06
begin = 2022-12-06 00:02:55.002206853+00:00
start-sync_0 = 00:08:53
start-zstd = 00:12:36
start-sync_1 = 00:26:17
end-sync_1 = 00:27:21
end = 2022-12-06 00:27:21.436376419+00:00

[server]
repo = "cake233/ubuntu-mate-amd64"

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
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
