# arch-cutefish-armv7

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
    --name arch-cutefish-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-cutefish-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-cutefish-armv7 zsh
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

## arch-cutefish-armv7.toml

```toml
[main]
name = "arch"
tag = ["cutefish", "2022-07-20"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-cutefish_armhf_2022-07-20_01-31.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a7800f17eed9d474fa1e5e8c22fa665b1d9d09f5eeebede9e08ec71d7b967612"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.5G"
tar_bytes = 3697442816

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1147015010

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220713"
previous_tag = "2022-07-13"
previous_file = "arch-cutefish_armhf_2022-07-13_01-11-rootfs.tar.zst"
previous_sha256 = "be32c04cb1eb98588faf11de5ac7b11222540d873ed227c5c238553ea0c7a7f7"

current_version = "latest01"
current_date = "20220720"
old_file = "arch-cutefish_armhf_2022-07-06_01-00-rootfs.tar.zst"
old_sha256 = "e200899d7353432c3c933bb85cd4fc37ecb5024ffaf7104c49945802cce71322"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-cutefish_armhf_2022-07-20_01-31-rootfs.tar.zst
# SHA256SUM=a7800f17eed9d474fa1e5e8c22fa665b1d9d09f5eeebede9e08ec71d7b967612
# BUILD_DATE=20220720
# BUILD_TAG=2022-07-20
# STATUS=completed
# VERSION=latest01
# END_TIME=01:31

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-20
begin = 2022-07-20 00:53:45.242062519+00:00
start-sync_0 = 01:10:55
start-zstd = 01:14:03
start-sync_1 = 01:29:53
end-sync_1 = 01:31:08
end = 2022-07-20 01:31:08.582476293+00:00

[server]
repo = "cake233/arch-cutefish-armv7"

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
