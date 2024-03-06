# debian-mate-arm64

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
    --name debian-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-mate-arm64 zsh
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

## debian-mate-arm64.toml

```toml
[main]
name = "debian"
tag = ["mate", "2024-03-06"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-mate_arm64_2024-03-06_14-34.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "76acf8db7ce9a85e2d909fe395e7f668adcd133b2d2b088e94aae76e21712c1f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.8G"
tar_bytes = 5050565120

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1302625582

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-mate_arm64_2023-11-22_13-50-rootfs.tar.zst"
previous_sha256 = "60859ea968113c1f31b102e01cd59379076a0dc72f276f0bc4f3347835ba96c1"

current_version = "latest01"
current_date = "20240306"
old_file = "debian-mate_arm64_2023-11-15_13-54-rootfs.tar.zst"
old_sha256 = "7809207b2ed7760cc5a304a2b54acfc41cb074a34c7edef6930f721b010569ce"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-mate_arm64_2024-03-06_14-34-rootfs.tar.zst
# SHA256SUM=76acf8db7ce9a85e2d909fe395e7f668adcd133b2d2b088e94aae76e21712c1f
# BUILD_DATE=20240306
# BUILD_TAG=2024-03-06
# STATUS=completed
# VERSION=latest01
# END_TIME=14:34

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-03-06
begin = 2024-03-06 12:41:37.725064918+00:00
start-sync_0 = 14:19:47
start-zstd = 14:22:13
start-sync_1 = 14:33:59
end-sync_1 = 14:34:58
end = 2024-03-06 14:34:58.401499100+00:00

[server]
repo = "cake233/debian-mate-arm64"

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
ldd = 'ldd (Debian GLIBC 2.37-15.1) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
