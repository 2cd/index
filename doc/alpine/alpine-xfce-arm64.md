# alpine-xfce-arm64

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
    --name alpine-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-xfce-arm64 zsh
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

## alpine-xfce-arm64.toml

```toml
[main]
name = "alpine"
tag = ["xfce", "2023-04-13"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_arm64_2023-04-13_00-21.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1270f78f4f6320e1e881b67eb941a3410904f68c56fd7575e4ed7de092fbfeca"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1348089856

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "419M"
zstd_bytes = 438599830

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230406"
previous_tag = "2023-04-06"
previous_file = "alpine-xfce_arm64_2023-04-06_00-26-rootfs.tar.zst"
previous_sha256 = "bc04dc5eba4fdfeac6a7ff48423aa086de1a8abcc103411c6c4c754daa3fa048"

current_version = "latest01"
current_date = "20230413"
old_file = "alpine-xfce_arm64_2023-03-30_00-22-rootfs.tar.zst"
old_sha256 = "4d702f6939887116d72d01847e8e3b7ff52b8436bc27630c2a8fc70d52ecb0fc"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-xfce_arm64_2023-04-13_00-21-rootfs.tar.zst
# SHA256SUM=1270f78f4f6320e1e881b67eb941a3410904f68c56fd7575e4ed7de092fbfeca
# BUILD_DATE=20230413
# BUILD_TAG=2023-04-13
# STATUS=completed
# VERSION=latest01
# END_TIME=00:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-13
begin = 2023-04-13 00:06:37.084516135+00:00
start-sync_0 = 00:15:28
start-zstd = 00:16:30
start-sync_1 = 00:20:51
end-sync_1 = 00:21:23
end = 2023-04-13 00:21:23.207092925+00:00

[server]
repo = "cake233/alpine-xfce-arm64"

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (aarch64) Version 1.2.3_git20230322'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
