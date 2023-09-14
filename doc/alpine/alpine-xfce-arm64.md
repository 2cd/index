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
tag = ["xfce", "2023-09-14"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_arm64_2023-09-14_00-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2c8a47598a701c3e13225cf71c685a8c91209b98b5fc21e74ecd2554e946f5be"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1326636032

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "400M"
zstd_bytes = 419022591

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230907"
previous_tag = "2023-09-07"
previous_file = "alpine-xfce_arm64_2023-09-07_00-18-rootfs.tar.zst"
previous_sha256 = "65369ed80cd424fbe3c139a745116a2e7df29841f44cb7c23a85d3e48483e44e"

current_version = "latest02"
current_date = "20230914"
old_file = "alpine-xfce_arm64_2023-08-31_00-17-rootfs.tar.zst"
old_sha256 = "5ec09175edbdeb95858de338999eb0698d12fde2efab26c50e2f8195bd24bd4f"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-xfce_arm64_2023-09-14_00-16-rootfs.tar.zst
# SHA256SUM=2c8a47598a701c3e13225cf71c685a8c91209b98b5fc21e74ecd2554e946f5be
# BUILD_DATE=20230914
# BUILD_TAG=2023-09-14
# STATUS=completed
# VERSION=latest02
# END_TIME=00:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-14
begin = 2023-09-14 00:07:26.865955179+00:00
start-sync_0 = 00:10:53
start-zstd = 00:11:49
start-sync_1 = 00:16:17
end-sync_1 = 00:16:49
end = 2023-09-14 00:16:49.959735843+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.4_git20230717'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
