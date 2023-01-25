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
tag = ["kde", "2023-01-25"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-kde_arm64_2023-01-25_01-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0c2c197e387c429656bd8ba100a998310647abb6370a67a5e200ce23f6a1b0fe"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.1G"
tar_bytes = 5423720448

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1542516008

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230111"
previous_tag = "2023-01-11"
previous_file = "arch-kde_arm64_2023-01-11_01-26-rootfs.tar.zst"
previous_sha256 = "31ab568910190cfe8a939a9b7b0d66e9f54db93fa6d9484323fd63368de829ad"

current_version = "latest01"
current_date = "20230125"
old_file = "arch-kde_arm64_2023-01-04_01-23-rootfs.tar.zst"
old_sha256 = "9fe7013cbc704fbf7844fca7c386d63a3960c4e4891cea2356e68b24b3d06fbb"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-kde_arm64_2023-01-25_01-29-rootfs.tar.zst
# SHA256SUM=0c2c197e387c429656bd8ba100a998310647abb6370a67a5e200ce23f6a1b0fe
# BUILD_DATE=20230125
# BUILD_TAG=2023-01-25
# STATUS=completed
# VERSION=latest01
# END_TIME=01:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-25
begin = 2023-01-25 00:31:05.107248160+00:00
start-sync_0 = 00:57:31
start-zstd = 01:03:49
start-sync_1 = 01:27:28
end-sync_1 = 01:29:08
end = 2023-01-25 01:29:08.568005273+00:00

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
