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
tag = ["lxde", "2024-03-06"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_i386_2024-03-06_13-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "47ca16c69eee9d83a29044b8cb4e677a02eb8d659609993dcec7225e64d18fff"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3167166976

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "813M"
zstd_bytes = 852167565

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-lxde_i386_2023-11-22_13-09-rootfs.tar.zst"
previous_sha256 = "f2c121cfc651a4d898063c1602a60ff6033acfdca607ff97a8fc0b2ec04c8649"

current_version = "latest01"
current_date = "20240306"
old_file = "debian-lxde_i386_2023-11-15_13-22-rootfs.tar.zst"
old_sha256 = "b8ee0fc44592ba743d4af1ecf4b197621d4e349e434c337223b4964877a5fa3f"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-lxde_i386_2024-03-06_13-11-rootfs.tar.zst
# SHA256SUM=47ca16c69eee9d83a29044b8cb4e677a02eb8d659609993dcec7225e64d18fff
# BUILD_DATE=20240306
# BUILD_TAG=2024-03-06
# STATUS=completed
# VERSION=latest01
# END_TIME=13:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-03-06
begin = 2024-03-06 12:41:35.632890807+00:00
start-sync_0 = 12:59:45
start-zstd = 13:01:31
start-sync_1 = 13:10:22
end-sync_1 = 13:11:00
end = 2024-03-06 13:11:00.251705933+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-15.1) 2.37'
zsh = ''

[port]
tcp = [5902, 36080]
```
