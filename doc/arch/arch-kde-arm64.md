# arch-kde-arm64

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
    --name arch-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-kde-arm64 zsh
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

## arch-kde-arm64.toml

```toml
[main]
name = "arch"
tag = ["kde", "2022-12-14"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-kde_arm64_2022-12-14_01-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "332ea01135a5e0af0abb6e60aec602c081b545eb2ef87d67945e8fae3c7a5592"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.1G"
tar_bytes = 5375657984

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1532441322

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221207"
previous_tag = "2022-12-07"
previous_file = "arch-kde_arm64_2022-12-07_01-18-rootfs.tar.zst"
previous_sha256 = "5a11c742fcfb20ceabbe8dc34fa6c363e9427c0b0b39e5fc198e8767c5f31b11"

current_version = "latest02"
current_date = "20221214"
old_file = "arch-kde_arm64_2022-11-30_01-18-rootfs.tar.zst"
old_sha256 = "cfd322f7f62a2987fedc518a5de8cb5419eafa6a8a8815917bed2bacdb4cc24d"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-kde_arm64_2022-12-14_01-26-rootfs.tar.zst
# SHA256SUM=332ea01135a5e0af0abb6e60aec602c081b545eb2ef87d67945e8fae3c7a5592
# BUILD_DATE=20221214
# BUILD_TAG=2022-12-14
# STATUS=completed
# VERSION=latest02
# END_TIME=01:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-14
begin = 2022-12-14 00:35:26.019773762+00:00
start-sync_0 = 00:56:34
start-zstd = 01:03:03
start-sync_1 = 01:24:37
end-sync_1 = 01:26:15
end = 2022-12-14 01:26:15.952741635+00:00

[server]
repo = "cake233/arch-kde-arm64"

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
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
