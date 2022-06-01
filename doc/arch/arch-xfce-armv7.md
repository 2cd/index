# arch-xfce-armv7

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not armv7, then install qemu & binfmt-support.
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
    --name arch-xfce-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-armv7 zsh
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

## arch-xfce-armv7.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2022-06-01"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_armhf_2022-06-01_00-57.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d1e6a72c2cc9ac22563b995992ccda8a91fcbcfda47f4d6749ce0e258a84f10c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.2G"
tar_bytes = 3390489088

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1108561381

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220525"
previous_tag = "2022-05-25"
previous_file = "arch-xfce_armhf_2022-05-25_01-06-rootfs.tar.zst"
previous_sha256 = "6462f0a7e28efc6302b806f3164fe0dd0e9a2f61bbd00c7d2b0da0c8822fd764"

current_version = "latest02"
current_date = "20220601"
old_file = "arch-xfce_armhf_2022-05-18_01-01-rootfs.tar.zst"
old_sha256 = "d1cb7b183ffa336637fe06e82eb560a4d411b53a5455688c96b39add01b2c7d9"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-xfce_armhf_2022-06-01_00-57-rootfs.tar.zst
# SHA256SUM=d1e6a72c2cc9ac22563b995992ccda8a91fcbcfda47f4d6749ce0e258a84f10c
# BUILD_DATE=20220601
# BUILD_TAG=2022-06-01
# STATUS=completed
# VERSION=latest02
# END_TIME=00:57

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-01
begin = 2022-06-01 00:29:52.358214428+00:00
start-sync_0 = 00:43:21
start-zstd = 00:45:58
start-sync_1 = 00:56:26
end-sync_1 = 00:57:33
end = 2022-06-01 00:57:33.663151518+00:00

[server]
repo = "cake233/arch-xfce-armv7"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (armv7l-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
