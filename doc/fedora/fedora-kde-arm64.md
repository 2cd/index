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
tag = ["kde", "2022-10-25"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_arm64_2022-10-25_14-58.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ab60a0d7cdf728de647e95442d98b255bc20c494f7fd7c7bf4a935b2303f89c9"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.8G"
tar_bytes = 7284190720

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.9G"
zstd_bytes = 1974003327

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221018"
previous_tag = "2022-10-18"
previous_file = "fedora-kde_arm64_2022-10-18_14-45-rootfs.tar.zst"
previous_sha256 = "e9879dff1f6920de0f37696358a39aa7667dff16346bb1397b725051f31b700c"

current_version = "latest02"
current_date = "20221025"
old_file = "fedora-kde_arm64_2022-10-11_14-40-rootfs.tar.zst"
old_sha256 = "c7eb03514d63597c1c2637775edaca270a8969ae435e1aefacd327f651b1a6a2"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-kde_arm64_2022-10-25_14-58-rootfs.tar.zst
# SHA256SUM=ab60a0d7cdf728de647e95442d98b255bc20c494f7fd7c7bf4a935b2303f89c9
# BUILD_DATE=20221025
# BUILD_TAG=2022-10-25
# STATUS=completed
# VERSION=latest02
# END_TIME=14:58

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-25
begin = 2022-10-25 12:49:24.147821515+00:00
start-sync_0 = 14:24:09
start-zstd = 14:30:41
start-sync_1 = 14:55:52
end-sync_1 = 14:58:04
end = 2022-10-25 14:58:04.834491604+00:00

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
