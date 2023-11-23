# alpine-mate-arm64

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
    --name alpine-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-mate-arm64 zsh
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

## alpine-mate-arm64.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2023-11-23"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_arm64_2023-11-23_00-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "aeb7aca0a3e298a6ce39c836569724a2f456fae0c3fd621f5256a8aa9efdff51"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "763M"
tar_bytes = 799600640

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "229M"
zstd_bytes = 239966953

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231116"
previous_tag = "2023-11-16"
previous_file = "alpine-mate_arm64_2023-11-16_00-11-rootfs.tar.zst"
previous_sha256 = "4ffe72248f8c34945450570e941662d1bc212e0723826f11293976037180731a"

current_version = "latest01"
current_date = "20231123"
old_file = "alpine-mate_arm64_2023-11-09_00-11-rootfs.tar.zst"
old_sha256 = "e6ad4920850c72c2ed09a5df0015d0d7052e6f309679bad5f0ca56142ef699b0"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-mate_arm64_2023-11-23_00-12-rootfs.tar.zst
# SHA256SUM=aeb7aca0a3e298a6ce39c836569724a2f456fae0c3fd621f5256a8aa9efdff51
# BUILD_DATE=20231123
# BUILD_TAG=2023-11-23
# STATUS=completed
# VERSION=latest01
# END_TIME=00:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-23
begin = 2023-11-23 00:07:49.317866821+00:00
start-sync_0 = 00:10:12
start-zstd = 00:10:39
start-sync_1 = 00:12:29
end-sync_1 = 00:12:45
end = 2023-11-23 00:12:45.204197055+00:00

[server]
repo = "cake233/alpine-mate-arm64"

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
