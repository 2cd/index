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
tag = ["cutefish", "2022-05-25"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-cutefish_arm64_2022-05-25_01-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "58b28b5a2f28b7777e5ec3f933fc00ace468df5c10353a7e2248390e1197ee30"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.4G"
tar_bytes = 4694891520

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1298574227

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220518"
previous_tag = "2022-05-18"
previous_file = "arch-cutefish_arm64_2022-05-18_01-12-rootfs.tar.zst"
previous_sha256 = "bb6a2444f1f5eafe4781ca4781de58155793e041483e0b4835a1b89301a88b8e"

current_version = "latest01"
current_date = "20220525"
old_file = "arch-cutefish_arm64_2022-05-11_01-21-rootfs.tar.zst"
old_sha256 = "c8994c38f37beab95eed805dffda23e18eef6c85783510cb534fa76dcb7e27ca"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-cutefish_arm64_2022-05-25_01-20-rootfs.tar.zst
# SHA256SUM=58b28b5a2f28b7777e5ec3f933fc00ace468df5c10353a7e2248390e1197ee30
# BUILD_DATE=20220525
# BUILD_TAG=2022-05-25
# STATUS=completed
# VERSION=latest01
# END_TIME=01:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-25
begin = 2022-05-25 00:29:54.296120307+00:00
start-sync_0 = 00:51:53
start-zstd = 00:57:41
start-sync_1 = 01:18:35
end-sync_1 = 01:20:03
end = 2022-05-25 01:20:03.209560206+00:00

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
