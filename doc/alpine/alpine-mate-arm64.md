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
tag = ["mate", "2023-10-19"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_arm64_2023-10-19_00-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2e731aa4b19a4762dab7a0e92e0a377baafa75e51e0a1313c24014e27f2d5193"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1303886336

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "377M"
zstd_bytes = 394920443

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231012"
previous_tag = "2023-10-12"
previous_file = "alpine-mate_arm64_2023-10-12_00-15-rootfs.tar.zst"
previous_sha256 = "1872dc6a1ab110b18366a64e2fc5e391f7c5c82d007502337b2d14b1e216b395"

current_version = "latest01"
current_date = "20231019"
old_file = "alpine-mate_arm64_2023-10-05_00-19-rootfs.tar.zst"
old_sha256 = "92a608172f6544cd0c8c42cef950366ac43d6ebc35cc6bd268b7119e8943a93d"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-mate_arm64_2023-10-19_00-18-rootfs.tar.zst
# SHA256SUM=2e731aa4b19a4762dab7a0e92e0a377baafa75e51e0a1313c24014e27f2d5193
# BUILD_DATE=20231019
# BUILD_TAG=2023-10-19
# STATUS=completed
# VERSION=latest01
# END_TIME=00:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-19
begin = 2023-10-19 00:07:07.422549727+00:00
start-sync_0 = 00:12:26
start-zstd = 00:13:36
start-sync_1 = 00:18:12
end-sync_1 = 00:18:49
end = 2023-10-19 00:18:49.125664100+00:00

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
