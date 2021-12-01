# arch-mate-amd64

## How to run it?

```shell
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
    --name arch-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it arch-mate-amd64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```shell
    startvnc
```

or

```shell
    startx11vnc
```

or

```shell
    novnc
```

Note:

If you want to use novnc, then open your browser, and type the address:

```
localhost:36081
```

If you want to use tiger/x11vnc, then open vnc viewer, then type the address:

```
localhost:5903
```

## arch-mate-amd64.toml

```toml
[main]
name = "arch"
tag = ["mate", "2021-12-01"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "arch-mate_amd64_2021-12-01_00-41.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "3c39662baad40ac9c74f9ce206f59cb8cb8f92540f6c53c6ed57265536e4c026"

# zstd: [1-22]
zstd-level = 15

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4750082560

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1459664274

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211128"
last_tag = "2021-11-28"
last_file = "arch-mate_amd64_2021-11-28_23-47-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211201"
old_file = "arch_amd64+mate-2021_11-03-rootfs.tar.zst"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-mate_amd64_2021-12-01_00-41-rootfs.tar.zst
# BUILD_DATE=20211201
# BUILD_TAG=2021-12-01
# STATUS=completed
# VERSION=latest02
# END_TIME=00:41

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-01
begin = 2021-12-01 00:21:29.132126505+00:00
start-sync_0 = 00:28:32
start-zstd = 00:33:26
start-sync_1 = 00:39:44
end-sync_1 = 00:41:13
end = 2021-12-01 00:41:13.097189211+00:00

[server]
repo = "cake233/arch-mate-amd64"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "us"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "global"
current = false
last = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"

[version]
zsh = 'zsh 5.8 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
