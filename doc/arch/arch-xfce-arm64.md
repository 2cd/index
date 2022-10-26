# arch-xfce-arm64

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
    --name arch-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-arm64 zsh
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

## arch-xfce-arm64.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2022-10-26"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_arm64_2022-10-26_01-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3b4452a697ac58b67d513454b52a83bdc34860a4e619f6c6da5ff40ae1eb4e0b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4342447616

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1271812167

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221019"
previous_tag = "2022-10-19"
previous_file = "arch-xfce_arm64_2022-10-19_01-09-rootfs.tar.zst"
previous_sha256 = "5a0c5d92b725160bc05938c37d1dea670be51a0288f9d1101baddca4b69a1a6d"

current_version = "latest02"
current_date = "20221026"
old_file = "arch-xfce_arm64_2022-10-12_01-09-rootfs.tar.zst"
old_sha256 = "c56fb9e6a193b879d2119903eab26c8e054cf474332734947957866e57c1e5aa"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-xfce_arm64_2022-10-26_01-13-rootfs.tar.zst
# SHA256SUM=3b4452a697ac58b67d513454b52a83bdc34860a4e619f6c6da5ff40ae1eb4e0b
# BUILD_DATE=20221026
# BUILD_TAG=2022-10-26
# STATUS=completed
# VERSION=latest02
# END_TIME=01:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-26
begin = 2022-10-26 00:27:25.024862615+00:00
start-sync_0 = 00:47:45
start-zstd = 00:52:32
start-sync_1 = 01:11:52
end-sync_1 = 01:13:19
end = 2022-10-26 01:13:19.421113613+00:00

[server]
repo = "cake233/arch-xfce-arm64"

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
