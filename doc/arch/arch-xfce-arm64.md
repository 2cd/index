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

## arch-xfce-arm64.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2023-05-24"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_arm64_2023-05-24_01-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "66ab5c72016eca56b536eccae9a0438095f647d59645514db4f1a5b197f4c3e2"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.3G"
tar_bytes = 4572747776

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1315318616

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230517"
previous_tag = "2023-05-17"
previous_file = "arch-xfce_arm64_2023-05-17_01-15-rootfs.tar.zst"
previous_sha256 = "59f0eb0627e76edff71921e03815bcdfc68fcd0f972e32e083e3614cfdd25181"

current_version = "latest01"
current_date = "20230524"
old_file = "arch-xfce_arm64_2023-05-10_01-20-rootfs.tar.zst"
old_sha256 = "3eddb0fda2ebefbcf14bf253c15eee914bb27fe4f41999513c6805c86f8d24f5"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-xfce_arm64_2023-05-24_01-14-rootfs.tar.zst
# SHA256SUM=66ab5c72016eca56b536eccae9a0438095f647d59645514db4f1a5b197f4c3e2
# BUILD_DATE=20230524
# BUILD_TAG=2023-05-24
# STATUS=completed
# VERSION=latest01
# END_TIME=01:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-24
begin = 2023-05-24 00:35:18.742651847+00:00
start-sync_0 = 00:52:32
start-zstd = 00:56:07
start-sync_1 = 01:13:06
end-sync_1 = 01:14:20
end = 2023-05-24 01:14:20.044530072+00:00

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
