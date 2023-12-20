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
tag = ["mate", "2023-12-20"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-mate_arm64_2023-12-20_13-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7527ebd8cf1e411a2cc0f5d52361f57cecc95432551127ae06b2967f738fe809"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4913271296

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1268205113

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-mate_arm64_2023-11-22_13-50-rootfs.tar.zst"
previous_sha256 = "60859ea968113c1f31b102e01cd59379076a0dc72f276f0bc4f3347835ba96c1"

current_version = "latest01"
current_date = "20231220"
old_file = "debian-mate_arm64_2023-11-15_13-54-rootfs.tar.zst"
old_sha256 = "7809207b2ed7760cc5a304a2b54acfc41cb074a34c7edef6930f721b010569ce"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-mate_arm64_2023-12-20_13-59-rootfs.tar.zst
# SHA256SUM=7527ebd8cf1e411a2cc0f5d52361f57cecc95432551127ae06b2967f738fe809
# BUILD_DATE=20231220
# BUILD_TAG=2023-12-20
# STATUS=completed
# VERSION=latest01
# END_TIME=13:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-20
begin = 2023-12-20 12:31:56.706983368+00:00
start-sync_0 = 13:44:52
start-zstd = 13:47:19
start-sync_1 = 13:58:58
end-sync_1 = 13:59:54
end = 2023-12-20 13:59:54.240790592+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-13) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
