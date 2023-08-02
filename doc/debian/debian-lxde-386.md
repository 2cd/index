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
tag = ["lxde", "2023-08-02"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_i386_2023-08-02_13-27.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "bac5767c6736d74c78fdc95a51ca2d8966cfc7a46a82c5c4bdab9ce117976dca"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4779964928

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1377641297

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230726"
previous_tag = "2023-07-26"
previous_file = "debian-lxde_i386_2023-07-26_13-23-rootfs.tar.zst"
previous_sha256 = "6c62c76e386f88c76246e722d46a0351fc16fa39a915d38867434d1cc14ef8d3"

current_version = "latest02"
current_date = "20230802"
old_file = "debian-lxde_i386_2023-07-19_13-34-rootfs.tar.zst"
old_sha256 = "decffe1537e05467092a8e16744d8f149e48b3baea3dedb67b6779fe9331dce3"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-lxde_i386_2023-08-02_13-27-rootfs.tar.zst
# SHA256SUM=bac5767c6736d74c78fdc95a51ca2d8966cfc7a46a82c5c4bdab9ce117976dca
# BUILD_DATE=20230802
# BUILD_TAG=2023-08-02
# STATUS=completed
# VERSION=latest02
# END_TIME=13:27

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-02
begin = 2023-08-02 12:22:57.991372181+00:00
start-sync_0 = 13:00:48
start-zstd = 13:05:42
start-sync_1 = 13:25:43
end-sync_1 = 13:27:27
end = 2023-08-02 13:27:27.842107516+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-6) 2.37'
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
