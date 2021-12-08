# arch-mate-arm64

## How to run it?

```shell
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
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
    --name arch-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it arch-mate-arm64 zsh
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

## arch-mate-arm64.toml

```toml
[main]
name = "arch"
tag = ["mate", "2021-12-08"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "arch-mate_arm64_2021-12-08_02-03.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "0f668ce6f5c3fa8dbc485004c8109ed4ff1202a91e1261eeafe20cd4555502f7"

# zstd: [1-22]
zstd-level = 15

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.9G"
tar_bytes = 5259729920

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1574061342

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211201"
last_tag = "2021-12-01"
last_file = "arch-mate_arm64_2021-12-01_01-01-rootfs.tar.zst"
last_sha256 = ""

current_version = "latest01"
current_date = "20211208"
old_file = "arch-mate_arm64_2021-11-29_00-02-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-mate_arm64_2021-12-08_02-03-rootfs.tar.zst
# SHA256SUM=0f668ce6f5c3fa8dbc485004c8109ed4ff1202a91e1261eeafe20cd4555502f7
# BUILD_DATE=20211208
# BUILD_TAG=2021-12-08
# STATUS=completed
# VERSION=latest01
# END_TIME=02:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-08
begin = 2021-12-08 01:28:17.837831647+00:00
start-sync_0 = 01:48:45
start-zstd = 01:54:18
start-sync_1 = 02:01:24
end-sync_1 = 02:03:01
end = 2021-12-08 02:03:01.910611812+00:00

[server]
repo = "cake233/arch-mate-arm64"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "azure"
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
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
