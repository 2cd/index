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
tag = ["lxde", "2023-10-18"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_i386_2023-10-18_13-38.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7d9b9f9f13bd9165826bb5523f425f77dbd0608cd87528d1cd637bcf3dc8e226"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.2G"
tar_bytes = 4418821120

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1234033973

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231011"
previous_tag = "2023-10-11"
previous_file = "debian-lxde_i386_2023-10-11_13-40-rootfs.tar.zst"
previous_sha256 = "74231035368934182e0728198c5947b77bfcfdcb596b694084bf17dd32bbdfd3"

current_version = "latest02"
current_date = "20231018"
old_file = "debian-lxde_i386_2023-10-04_13-33-rootfs.tar.zst"
old_sha256 = "01314c220c5cd1dd5c51469b4001155f4ad8c9bbdcd4e3bc3bdecd6ebbe893f0"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-lxde_i386_2023-10-18_13-38-rootfs.tar.zst
# SHA256SUM=7d9b9f9f13bd9165826bb5523f425f77dbd0608cd87528d1cd637bcf3dc8e226
# BUILD_DATE=20231018
# BUILD_TAG=2023-10-18
# STATUS=completed
# VERSION=latest02
# END_TIME=13:38

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-18
begin = 2023-10-18 12:46:13.109625295+00:00
start-sync_0 = 13:16:22
start-zstd = 13:19:47
start-sync_1 = 13:36:36
end-sync_1 = 13:38:08
end = 2023-10-18 13:38:08.728189700+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
