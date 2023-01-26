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
tag = ["kde", "2023-01-26"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-kde_arm64_2023-01-26_00-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ab766264014a6161a64cad008df7f3cf7d23b9c8bbf3548e3e072cbc74afb706"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1921890304

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "519M"
zstd_bytes = 543514721

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230119"
previous_tag = "2023-01-19"
previous_file = "alpine-kde_arm64_2023-01-19_00-24-rootfs.tar.zst"
previous_sha256 = "02eec3afd0243d9d5dc530c6df5255ee6cbf169f9287e752244698e9f8985cd6"

current_version = "latest02"
current_date = "20230126"
old_file = "alpine-kde_arm64_2023-01-12_00-27-rootfs.tar.zst"
old_sha256 = "0bd0d5e0de541cec7506aa69f6a3550d2667599c42ca94841474819c623579f3"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-kde_arm64_2023-01-26_00-26-rootfs.tar.zst
# SHA256SUM=ab766264014a6161a64cad008df7f3cf7d23b9c8bbf3548e3e072cbc74afb706
# BUILD_DATE=20230126
# BUILD_TAG=2023-01-26
# STATUS=completed
# VERSION=latest02
# END_TIME=00:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-26
begin = 2023-01-26 00:07:06.890141385+00:00
start-sync_0 = 00:17:13
start-zstd = 00:18:56
start-sync_1 = 00:25:49
end-sync_1 = 00:26:30
end = 2023-01-26 00:26:30.490230209+00:00

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
