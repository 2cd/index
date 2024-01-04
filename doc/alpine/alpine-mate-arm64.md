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
tag = ["mate", "2024-01-04"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_arm64_2024-01-04_00-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1c5d40aac455f2e24f559ecce7004042def8d985cd034a195fa5da9f63af27d8"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1319768576

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "381M"
zstd_bytes = 399182453

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231123"
previous_tag = "2023-11-23"
previous_file = "alpine-mate_arm64_2023-11-23_00-12-rootfs.tar.zst"
previous_sha256 = "aeb7aca0a3e298a6ce39c836569724a2f456fae0c3fd621f5256a8aa9efdff51"

current_version = "latest02"
current_date = "20240104"
old_file = "alpine-mate_arm64_2023-11-16_00-11-rootfs.tar.zst"
old_sha256 = "4ffe72248f8c34945450570e941662d1bc212e0723826f11293976037180731a"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-mate_arm64_2024-01-04_00-14-rootfs.tar.zst
# SHA256SUM=1c5d40aac455f2e24f559ecce7004042def8d985cd034a195fa5da9f63af27d8
# BUILD_DATE=20240104
# BUILD_TAG=2024-01-04
# STATUS=completed
# VERSION=latest02
# END_TIME=00:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-04
begin = 2024-01-04 00:07:02.992412362+00:00
start-sync_0 = 00:10:24
start-zstd = 00:11:10
start-sync_1 = 00:14:20
end-sync_1 = 00:14:44
end = 2024-01-04 00:14:44.222541870+00:00

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
