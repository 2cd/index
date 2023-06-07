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
tag = ["lxde", "2023-06-07"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_i386_2023-06-07_13-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "41a1df984749804b45f9ab6a158809dc2eda288046de4db6593a2223336ed8e9"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4323793920

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1223390294

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230531"
previous_tag = "2023-05-31"
previous_file = "debian-lxde_i386_2023-05-31_13-14-rootfs.tar.zst"
previous_sha256 = "f6201f78217b6cf2bc37d8f1109e534cb11b334fe731e1d0610c22807a135049"

current_version = "latest02"
current_date = "20230607"
old_file = "debian-lxde_i386_2023-05-24_13-23-rootfs.tar.zst"
old_sha256 = "95c2e93cc8ed105e810bfa73c1c8548aa56fdb6660f26c5c83a37cfef153d80f"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-lxde_i386_2023-06-07_13-16-rootfs.tar.zst
# SHA256SUM=41a1df984749804b45f9ab6a158809dc2eda288046de4db6593a2223336ed8e9
# BUILD_DATE=20230607
# BUILD_TAG=2023-06-07
# STATUS=completed
# VERSION=latest02
# END_TIME=13:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-07
begin = 2023-06-07 12:24:54.140515473+00:00
start-sync_0 = 12:54:55
start-zstd = 12:58:19
start-sync_1 = 13:14:58
end-sync_1 = 13:16:11
end = 2023-06-07 13:16:11.625997614+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
