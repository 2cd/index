# debian-mate-amd64

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
    --name debian-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-mate-amd64 zsh
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

## debian-mate-amd64.toml

```toml
[main]
name = "debian"
tag = ["mate", "2022-07-27"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-mate_amd64_2022-07-27_12-52.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "aabe92d9f4f9dd1bfce3430dd18f4c88a8ca51cca370c6bdf2ee5a04d1d65c0f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4869126144

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1349658307

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220713"
previous_tag = "2022-07-13"
previous_file = "debian-mate_amd64_2022-07-13_12-47-rootfs.tar.zst"
previous_sha256 = "d9203811166b31aa86352c4712eb865f8797c6546a8b499a852c6d4dca9f95b9"

current_version = "latest01"
current_date = "20220727"
old_file = "debian-mate_amd64_2022-07-06_12-43-rootfs.tar.zst"
old_sha256 = "40dcc66bc2be552516f9784e91fde995c9b5a907801bb1357275c33b7034ecdd"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-mate_amd64_2022-07-27_12-52-rootfs.tar.zst
# SHA256SUM=aabe92d9f4f9dd1bfce3430dd18f4c88a8ca51cca370c6bdf2ee5a04d1d65c0f
# BUILD_DATE=20220727
# BUILD_TAG=2022-07-27
# STATUS=completed
# VERSION=latest01
# END_TIME=12:52

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-27
begin = 2022-07-27 12:22:03.939346104+00:00
start-sync_0 = 12:28:13
start-zstd = 12:32:53
start-sync_1 = 12:50:51
end-sync_1 = 12:52:19
end = 2022-07-27 12:52:19.341247107+00:00

[server]
repo = "cake233/debian-mate-amd64"

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
ldd = 'ldd (Debian GLIBC 2.33-8) 2.33'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
