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
tag = ["xfce", "2023-08-31"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_arm64_2023-08-31_00-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5ec09175edbdeb95858de338999eb0698d12fde2efab26c50e2f8195bd24bd4f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1335652864

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "409M"
zstd_bytes = 428643937

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230824"
previous_tag = "2023-08-24"
previous_file = "alpine-xfce_arm64_2023-08-24_00-18-rootfs.tar.zst"
previous_sha256 = "e62d1d8b6b24964ee65630c54b8d88fd83f099976818f6ed46411e42cf3c1157"

current_version = "latest02"
current_date = "20230831"
old_file = "alpine-xfce_arm64_2023-08-17_00-16-rootfs.tar.zst"
old_sha256 = "fcdf7517fb0d372a138e8f1d9b37f1696341d9327a555a480614fb305217d9ad"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-xfce_arm64_2023-08-31_00-17-rootfs.tar.zst
# SHA256SUM=5ec09175edbdeb95858de338999eb0698d12fde2efab26c50e2f8195bd24bd4f
# BUILD_DATE=20230831
# BUILD_TAG=2023-08-31
# STATUS=completed
# VERSION=latest02
# END_TIME=00:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-31
begin = 2023-08-31 00:07:58.039233202+00:00
start-sync_0 = 00:11:22
start-zstd = 00:12:19
start-sync_1 = 00:16:30
end-sync_1 = 00:17:04
end = 2023-08-31 00:17:04.141036223+00:00

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
