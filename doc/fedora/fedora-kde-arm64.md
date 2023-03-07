# fedora-kde-arm64

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
    --name fedora-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-kde-arm64 zsh
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

## fedora-kde-arm64.toml

```toml
[main]
name = "fedora"
tag = ["kde", "2023-03-07"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_arm64_2023-03-07_15-40.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "86d06918cdfef47c576db3f03697b2c03db713298396f63d276447019572ede0"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "7.2G"
tar_bytes = 7686866944

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.9G"
zstd_bytes = 2004220550

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230228"
previous_tag = "2023-02-28"
previous_file = "fedora-kde_arm64_2023-02-28_15-39-rootfs.tar.zst"
previous_sha256 = "ed988d89240edc31de7813ec68d5300c04b22a1ff42b9b361145533431eb1ab8"

current_version = "latest01"
current_date = "20230307"
old_file = "fedora-kde_arm64_2023-02-21_15-42-rootfs.tar.zst"
old_sha256 = "4d556631d628c3d6587af239550265af67f982e018b810834351d1b60199ca2e"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-kde_arm64_2023-03-07_15-40-rootfs.tar.zst
# SHA256SUM=86d06918cdfef47c576db3f03697b2c03db713298396f63d276447019572ede0
# BUILD_DATE=20230307
# BUILD_TAG=2023-03-07
# STATUS=completed
# VERSION=latest01
# END_TIME=15:40

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-07
begin = 2023-03-07 13:05:16.711212778+00:00
start-sync_0 = 15:10:34
start-zstd = 15:16:20
start-sync_1 = 15:38:56
end-sync_1 = 15:40:57
end = 2023-03-07 15:40:57.792624157+00:00

[server]
repo = "cake233/fedora-kde-arm64"

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
