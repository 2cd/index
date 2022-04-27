# arch-cutefish-arm64

## How to run it?

```sh
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
    --name arch-cutefish-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-cutefish-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-cutefish-arm64 zsh
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

## arch-cutefish-arm64.toml

```toml
[main]
name = "arch"
tag = ["cutefish", "2022-04-27"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-cutefish_arm64_2022-04-27_01-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "db1abdb53274d77466b854c3792a71eb1abb9ac7ae0bc7ba87011649e70ebf9c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4749492224

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1293468666

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220420"
previous_tag = "2022-04-20"
previous_file = "arch-cutefish_arm64_2022-04-20_01-04-rootfs.tar.zst"
previous_sha256 = "25cb5c3f421e307ed995e236b57d5e803d74925c3958942a69baca03f46a0a2f"

current_version = "latest01"
current_date = "20220427"
old_file = "arch-cutefish_arm64_2022-04-13_01-18-rootfs.tar.zst"
old_sha256 = "878a8eb09c9b67a0a362dd138b4a6d5fc054a0571e79207b8fb5d5e5255bad15"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-cutefish_arm64_2022-04-27_01-07-rootfs.tar.zst
# SHA256SUM=db1abdb53274d77466b854c3792a71eb1abb9ac7ae0bc7ba87011649e70ebf9c
# BUILD_DATE=20220427
# BUILD_TAG=2022-04-27
# STATUS=completed
# VERSION=latest01
# END_TIME=01:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-27
begin = 2022-04-27 00:29:53.218648500+00:00
start-sync_0 = 00:46:08
start-zstd = 00:50:19
start-sync_1 = 01:06:04
end-sync_1 = 01:07:24
end = 2022-04-27 01:07:24.249119658+00:00

[server]
repo = "cake233/arch-cutefish-arm64"

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
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
