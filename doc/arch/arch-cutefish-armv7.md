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
tag = ["cutefish", "2022-05-18"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-cutefish_armhf_2022-05-18_00-57.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1c02debd306303793e61e825b95d4ae1a6d4f4ed48b2c8404d70f8b6f9e7cc5c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3831827968

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1155514877

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220511"
previous_tag = "2022-05-11"
previous_file = "arch-cutefish_armhf_2022-05-11_01-04-rootfs.tar.zst"
previous_sha256 = "05f8f6da2c5d3f02a5ff74e84ca00b9f998f1086c21dade00aa911036e00e1ca"

current_version = "latest02"
current_date = "20220518"
old_file = "arch-cutefish_armhf_2022-05-04_01-02-rootfs.tar.zst"
old_sha256 = "4c7d79b6162a29bac5a84367e4e87ff6e6f5d528e758737e417a7882028dbae5"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-cutefish_armhf_2022-05-18_00-57-rootfs.tar.zst
# SHA256SUM=1c02debd306303793e61e825b95d4ae1a6d4f4ed48b2c8404d70f8b6f9e7cc5c
# BUILD_DATE=20220518
# BUILD_TAG=2022-05-18
# STATUS=completed
# VERSION=latest02
# END_TIME=00:57

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-18
begin = 2022-05-18 00:27:16.223744164+00:00
start-sync_0 = 00:40:35
start-zstd = 00:43:59
start-sync_1 = 00:56:37
end-sync_1 = 00:57:51
end = 2022-05-18 00:57:51.581931113+00:00

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
