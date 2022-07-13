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
tag = ["cutefish", "2022-07-13"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-cutefish_arm64_2022-07-13_01-19.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3ca037b716b7450bdc2863695ee32110b6a78214e544879187a9daa9295092ed"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4740027904

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1320188382

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220706"
previous_tag = "2022-07-06"
previous_file = "arch-cutefish_arm64_2022-07-06_01-16-rootfs.tar.zst"
previous_sha256 = "c48e5d8e173f270db1a95ff55c4c5de0b4dcb7191e426b27499f65a0a50a2f39"

current_version = "latest02"
current_date = "20220713"
old_file = "arch-cutefish_arm64_2022-06-29_01-12-rootfs.tar.zst"
old_sha256 = "2f89bd18f1a0666cb2d2dc7ee2a84ea4c5158e00da772f0b3aadeb41fbb333c9"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-cutefish_arm64_2022-07-13_01-19-rootfs.tar.zst
# SHA256SUM=3ca037b716b7450bdc2863695ee32110b6a78214e544879187a9daa9295092ed
# BUILD_DATE=20220713
# BUILD_TAG=2022-07-13
# STATUS=completed
# VERSION=latest02
# END_TIME=01:19

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-13
begin = 2022-07-13 00:37:51.873021414+00:00
start-sync_0 = 00:55:50
start-zstd = 01:00:02
start-sync_1 = 01:18:03
end-sync_1 = 01:19:20
end = 2022-07-13 01:19:20.473855055+00:00

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
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
