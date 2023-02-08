# debian-lxde-386

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not 386, then install qemu & binfmt-support.
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
    --name debian-lxde-386 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-lxde-386

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-lxde-386 zsh
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

## debian-lxde-386.toml

```toml
[main]
name = "debian"
tag = ["lxde", "2023-02-08"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_i386_2023-02-08_13-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "eb5da37b4d38269edc5240aeaae0ac8f1e14b7157f5500b4f94e59f5069332e6"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4289637376

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1214124191

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230201"
previous_tag = "2023-02-01"
previous_file = "debian-lxde_i386_2023-02-01_13-15-rootfs.tar.zst"
previous_sha256 = "91b00a51d2650521dfee07620846cc4bdabe14bfda99caa4a4d19aa1880c013d"

current_version = "latest02"
current_date = "20230208"
old_file = "debian-lxde_i386_2023-01-25_13-12-rootfs.tar.zst"
old_sha256 = "30a030d133305a66ffc5258956270b4f4178df1aa711bf42b71004ca0b80a6ce"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-lxde_i386_2023-02-08_13-20-rootfs.tar.zst
# SHA256SUM=eb5da37b4d38269edc5240aeaae0ac8f1e14b7157f5500b4f94e59f5069332e6
# BUILD_DATE=20230208
# BUILD_TAG=2023-02-08
# STATUS=completed
# VERSION=latest02
# END_TIME=13:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-08
begin = 2023-02-08 12:22:35.330617989+00:00
start-sync_0 = 12:58:07
start-zstd = 13:02:06
start-sync_1 = 13:19:28
end-sync_1 = 13:20:51
end = 2023-02-08 13:20:51.055204238+00:00

[server]
repo = "cake233/debian-lxde-386"

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
