# manjaro-xfce-arm64

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
    --name manjaro-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/manjaro-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it manjaro-xfce-arm64 zsh
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

## manjaro-xfce-arm64.toml

```toml
[main]
name = "manjaro"
tag = ["xfce", "2022-05-27"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_arm64_2022-05-27_12-54.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "21638bfb1e375c742ec4a48dc6d1c5a636412a1100b83a1d0b9fbcc44f47da9b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.3G"
tar_bytes = 4557044736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1287754618

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220520"
previous_tag = "2022-05-20"
previous_file = "manjaro-xfce_arm64_2022-05-20_12-53-rootfs.tar.zst"
previous_sha256 = "aa1ca89dbe681f802349f2492db40b673ca3019b28c5c0b180687a0459fbcd40"

current_version = "latest02"
current_date = "20220527"
old_file = "manjaro-xfce_arm64_2022-05-13_12-50-rootfs.tar.zst"
old_sha256 = "f7e90dbf88d0a83a175b65349da5443d91789953c923f0014d165a0b71091f20"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-xfce_arm64_2022-05-27_12-54-rootfs.tar.zst
# SHA256SUM=21638bfb1e375c742ec4a48dc6d1c5a636412a1100b83a1d0b9fbcc44f47da9b
# BUILD_DATE=20220527
# BUILD_TAG=2022-05-27
# STATUS=completed
# VERSION=latest02
# END_TIME=12:54

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-27
begin = 2022-05-27 12:20:54.034918700+00:00
start-sync_0 = 12:33:27
start-zstd = 12:37:22
start-sync_1 = 12:53:16
end-sync_1 = 12:54:33
end = 2022-05-27 12:54:33.276310800+00:00

[server]
repo = "cake233/manjaro-xfce-arm64"

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
