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
tag = ["xfce", "2023-06-23"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_arm64_2023-06-23_13-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f77de859195b21d39d4aead76474b2ea41f7b81e17be4e966d560e6dc791cdaf"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.3G"
tar_bytes = 4599037440

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1320962560

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230616"
previous_tag = "2023-06-16"
previous_file = "manjaro-xfce_arm64_2023-06-16_12-54-rootfs.tar.zst"
previous_sha256 = "38ea8ad0667b36cef7500c23f6d28ac14473bb7371a2d2bd3d2070f66a446fcd"

current_version = "latest01"
current_date = "20230623"
old_file = "manjaro-xfce_arm64_2023-06-09_12-59-rootfs.tar.zst"
old_sha256 = "04b998532d0dd0333be4834dd3ff4df668220f22350350a96a364c6c5c7f3343"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-xfce_arm64_2023-06-23_13-01-rootfs.tar.zst
# SHA256SUM=f77de859195b21d39d4aead76474b2ea41f7b81e17be4e966d560e6dc791cdaf
# BUILD_DATE=20230623
# BUILD_TAG=2023-06-23
# STATUS=completed
# VERSION=latest01
# END_TIME=13:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-23
begin = 2023-06-23 12:23:41.012996349+00:00
start-sync_0 = 12:40:57
start-zstd = 12:44:43
start-sync_1 = 13:00:47
end-sync_1 = 13:01:59
end = 2023-06-23 13:01:59.657926919+00:00

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
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
