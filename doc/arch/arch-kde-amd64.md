# arch-kde-amd64

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
    --name arch-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-kde-amd64 zsh
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

## arch-kde-amd64.toml

```toml
[main]
name = "arch"
tag = ["kde", "2022-11-09"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-kde_amd64_2022-11-09_00-37.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d83ec441f85f6751b6ac305ab462d39736664bcd8d23219e70e2bfdd06f79ffd"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4808309248

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1403715049

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221102"
previous_tag = "2022-11-02"
previous_file = "arch-kde_amd64_2022-11-02_00-42-rootfs.tar.zst"
previous_sha256 = "7a444070987a1b619f94f50ec2f31381759a25f4e43cf0f6b71e5f688511426f"

current_version = "latest02"
current_date = "20221109"
old_file = "arch-kde_amd64_2022-10-26_00-53-rootfs.tar.zst"
old_sha256 = "905b47b1eb49566c231448e1ac2245d836d861c6741a4328087eef2e01ac401a"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-kde_amd64_2022-11-09_00-37-rootfs.tar.zst
# SHA256SUM=d83ec441f85f6751b6ac305ab462d39736664bcd8d23219e70e2bfdd06f79ffd
# BUILD_DATE=20221109
# BUILD_TAG=2022-11-09
# STATUS=completed
# VERSION=latest02
# END_TIME=00:37

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-09
begin = 2022-11-09 00:09:07.047938330+00:00
start-sync_0 = 00:13:40
start-zstd = 00:18:31
start-sync_1 = 00:35:53
end-sync_1 = 00:37:12
end = 2022-11-09 00:37:12.644722479+00:00

[server]
repo = "cake233/arch-kde-amd64"

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
ldd = 'ldd (GNU libc) 2.36'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
