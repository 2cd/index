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
tag = ["lxde", "2022-10-05"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_i386_2022-10-05_13-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3a9132780a08a18103629ffb389475bda44f0cfaea030d5c367a7bfc6139b766"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.9G"
tar_bytes = 4156788736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1184109844

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220928"
previous_tag = "2022-09-28"
previous_file = "debian-lxde_i386_2022-09-28_13-10-rootfs.tar.zst"
previous_sha256 = "699171ab49a5fbd5d60a9ab665b3c55ef0d4c70c36ae1435bcad0fdcfc55edc4"

current_version = "latest01"
current_date = "20221005"
old_file = "debian-lxde_i386_2022-09-21_13-15-rootfs.tar.zst"
old_sha256 = "564404231aa669f68f25cf58aa9f0ab335925622ef180c8258d0791c1e721660"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-lxde_i386_2022-10-05_13-09-rootfs.tar.zst
# SHA256SUM=3a9132780a08a18103629ffb389475bda44f0cfaea030d5c367a7bfc6139b766
# BUILD_DATE=20221005
# BUILD_TAG=2022-10-05
# STATUS=completed
# VERSION=latest01
# END_TIME=13:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-05
begin = 2022-10-05 12:23:04.124339757+00:00
start-sync_0 = 12:51:40
start-zstd = 12:55:03
start-sync_1 = 13:08:42
end-sync_1 = 13:09:46
end = 2022-10-05 13:09:47.016515463+00:00

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
ldd = 'ldd (Debian GLIBC 2.35-2) 2.35'
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
