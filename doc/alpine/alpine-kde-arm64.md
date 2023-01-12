# alpine-kde-arm64

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
    --name alpine-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-kde-arm64 zsh
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

## alpine-kde-arm64.toml

```toml
[main]
name = "alpine"
tag = ["kde", "2023-01-12"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-kde_arm64_2023-01-12_00-27.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0bd0d5e0de541cec7506aa69f6a3550d2667599c42ca94841474819c623579f3"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1921311744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "522M"
zstd_bytes = 547021053

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230105"
previous_tag = "2023-01-05"
previous_file = "alpine-kde_arm64_2023-01-05_00-24-rootfs.tar.zst"
previous_sha256 = "77271eb3599bbd9f170a4fea7ef96d5016259806d14c01b8f4cda21abc3e5138"

current_version = "latest02"
current_date = "20230112"
old_file = "alpine-kde_arm64_2022-12-29_00-23-rootfs.tar.zst"
old_sha256 = "4247a2274f74022f4aaeb05f4fedc750d928a6df718974880f9856d3ab6fe069"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-kde_arm64_2023-01-12_00-27-rootfs.tar.zst
# SHA256SUM=0bd0d5e0de541cec7506aa69f6a3550d2667599c42ca94841474819c623579f3
# BUILD_DATE=20230112
# BUILD_TAG=2023-01-12
# STATUS=completed
# VERSION=latest02
# END_TIME=00:27

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-12
begin = 2023-01-12 00:07:02.229843889+00:00
start-sync_0 = 00:17:51
start-zstd = 00:19:38
start-sync_1 = 00:26:41
end-sync_1 = 00:27:24
end = 2023-01-12 00:27:24.735469462+00:00

[server]
repo = "cake233/alpine-kde-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.3'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
