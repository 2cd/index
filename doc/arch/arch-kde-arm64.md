# arch-kde-arm64

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
    --name arch-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-kde-arm64 zsh
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

## arch-kde-arm64.toml

```toml
[main]
name = "arch"
tag = ["kde", "2022-04-05"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "arch-kde_arm64_2022-04-06_00-11.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "a5adfae1e0a7ec7499de073454d4d3725cba1e14fb68d355f5eaa0f5a773f94a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.9G"
tar_bytes = 5157493760

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1439126999

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220330"
previous_tag = "2022-03-29"
previous_file = "arch-kde_arm64_2022-03-30_00-13-rootfs.tar.zst"
previous_sha256 = "30f2f49629217d9421e3068dd81a582a7a300a1059950f8fe565174eab3d0b73"

current_version = "latest01"
current_date = "20220406"
old_file = "arch-kde_arm64_2022-03-23_01-04-rootfs.tar.zst"
old_sha256 = "d3bff351ba4a8ae5d2f9e30adf4d981d9e868de342d35110cb10891fc5eb005b"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-kde_arm64_2022-04-06_00-11-rootfs.tar.zst
# SHA256SUM=a5adfae1e0a7ec7499de073454d4d3725cba1e14fb68d355f5eaa0f5a773f94a
# BUILD_DATE=20220406
# BUILD_TAG=2022-04-05
# STATUS=completed
# VERSION=latest01
# END_TIME=00:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-05
begin = 2022-04-05 23:30:21.034672245+00:00
start-sync_0 = 23:47:45
start-zstd = 23:52:48
start-sync_1 = 00:09:43
end-sync_1 = 00:11:03
end = 2022-04-06 00:11:03.314011102+00:00

[server]
repo = "cake233/arch-kde-arm64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
