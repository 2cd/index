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
tag = ["mate", "2022-11-01", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-mate_amd64_2022-11-01_00-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "db48b40d27e356223c4a4b84cf0bc93d65b425ec64b51420741a389bd7da3a24"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4229505536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1132171117

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221025"
previous_tag = "2022-10-25"
previous_file = "ubuntu-mate_amd64_2022-10-25_00-51-rootfs.tar.zst"
previous_sha256 = "283cbd4426f7f85a71119b2392c07c070b240b0149459c04b3cf35b17fc82161"

current_version = "latest02"
current_date = "20221101"
old_file = "ubuntu-mate_amd64_2022-10-18_00-49-rootfs.tar.zst"
old_sha256 = "f729cf9c930c3b37b356b513a4f6592b0de71256442108282a611b602c69dc9b"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-mate_amd64_2022-11-01_00-26-rootfs.tar.zst
# SHA256SUM=db48b40d27e356223c4a4b84cf0bc93d65b425ec64b51420741a389bd7da3a24
# BUILD_DATE=20221101
# BUILD_TAG=2022-11-01
# STATUS=completed
# VERSION=latest02
# END_TIME=00:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-01
begin = 2022-11-01 00:02:50.191391083+00:00
start-sync_0 = 00:08:11
start-zstd = 00:11:47
start-sync_1 = 00:25:02
end-sync_1 = 00:26:05
end = 2022-11-01 00:26:05.708943748+00:00

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
