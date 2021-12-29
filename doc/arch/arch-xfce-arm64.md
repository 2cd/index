# arch-xfce-arm64

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
    --name arch-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-arm64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```sh
    startvnc
```

or

```sh
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

## arch-xfce-arm64.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2021-12-29"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "arch-xfce_arm64_2021-12-29_00-59.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "921558320639aba43ec65032e038676f7fd7cf1b538c4f7a32a2045e11b04f17"

# zstd: [1-22]
zstd-level = 15

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4376762880

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1380163337

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211222"
previous_tag = "2021-12-22"
previous_file = "arch-xfce_arm64_2021-12-22_00-54-rootfs.tar.zst"
previous_sha256 = "46d8fc1177530b660f14277ae291a10232c59a8a9d38d7e4deaf0504ac46cf29"

current_version = "latest01"
current_date = "20211229"
old_file = "arch-xfce_arm64_2021-12-15_00-50-rootfs.tar.zst"
old_sha256 = "3a4d3b0aa700efc2907bb64e84c7df8b659e08f85b117b1ac0408e2249ea1198"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-xfce_arm64_2021-12-29_00-59-rootfs.tar.zst
# SHA256SUM=921558320639aba43ec65032e038676f7fd7cf1b538c4f7a32a2045e11b04f17
# BUILD_DATE=20211229
# BUILD_TAG=2021-12-29
# STATUS=completed
# VERSION=latest01
# END_TIME=00:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-29
begin = 2021-12-29 00:22:39.178706818+00:00
start-sync_0 = 00:47:00
start-zstd = 00:51:35
start-sync_1 = 00:57:40
end-sync_1 = 00:59:14
end = 2021-12-29 00:59:14.641457824+00:00

[server]
repo = "cake233/arch-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.32'
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
