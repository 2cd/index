# arch-mate-arm64

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
    --name arch-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-mate-arm64 zsh
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

## arch-mate-arm64.toml

```toml
[main]
name = "arch"
tag = ["mate", "2022-04-27"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-mate_arm64_2022-04-27_01-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4a32521920bc1571168dc5f559bf8a8e6f19ce0e99afeee0a1a1c5a25cb4dba6"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.0G"
tar_bytes = 5266500096

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1443520483

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220420"
previous_tag = "2022-04-20"
previous_file = "arch-mate_arm64_2022-04-20_01-09-rootfs.tar.zst"
previous_sha256 = "ec8afac78f63fe3d53b8547fd4607214246e76147f0f27314f19f2bf3d7bc17e"

current_version = "latest01"
current_date = "20220427"
old_file = "arch-mate_arm64_2022-04-13_01-16-rootfs.tar.zst"
old_sha256 = "37fdc80cb1fdffa3611d5c7163e93b087119a9437740bd926e86402f9d816ff8"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-mate_arm64_2022-04-27_01-11-rootfs.tar.zst
# SHA256SUM=4a32521920bc1571168dc5f559bf8a8e6f19ce0e99afeee0a1a1c5a25cb4dba6
# BUILD_DATE=20220427
# BUILD_TAG=2022-04-27
# STATUS=completed
# VERSION=latest01
# END_TIME=01:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-27
begin = 2022-04-27 00:29:57.411420627+00:00
start-sync_0 = 00:47:21
start-zstd = 00:52:23
start-sync_1 = 01:10:30
end-sync_1 = 01:11:58
end = 2022-04-27 01:11:59.009069686+00:00

[server]
repo = "cake233/arch-mate-arm64"

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
