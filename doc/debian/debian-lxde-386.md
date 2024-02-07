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
tag = ["lxde", "2024-02-07"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_i386_2024-02-07_13-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e77f767c8879040e6981c9ced61c04aaec626f645c31ab107656e4e181521de3"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.3G"
tar_bytes = 4538055680

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1255835130

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-lxde_i386_2023-11-22_13-09-rootfs.tar.zst"
previous_sha256 = "f2c121cfc651a4d898063c1602a60ff6033acfdca607ff97a8fc0b2ec04c8649"

current_version = "latest01"
current_date = "20240207"
old_file = "debian-lxde_i386_2023-11-15_13-22-rootfs.tar.zst"
old_sha256 = "b8ee0fc44592ba743d4af1ecf4b197621d4e349e434c337223b4964877a5fa3f"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-lxde_i386_2024-02-07_13-11-rootfs.tar.zst
# SHA256SUM=e77f767c8879040e6981c9ced61c04aaec626f645c31ab107656e4e181521de3
# BUILD_DATE=20240207
# BUILD_TAG=2024-02-07
# STATUS=completed
# VERSION=latest01
# END_TIME=13:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-07
begin = 2024-02-07 12:33:26.636545740+00:00
start-sync_0 = 12:56:41
start-zstd = 12:59:10
start-sync_1 = 13:10:35
end-sync_1 = 13:11:27
end = 2024-02-07 13:11:27.138192869+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-15) 2.37'
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
