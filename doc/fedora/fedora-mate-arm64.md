# fedora-mate-arm64

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
    --name fedora-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-arm64 zsh
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

## fedora-mate-arm64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2022-10-11"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_arm64_2022-10-11_15-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4a240f0f7e2eefbea85b8cce79e6e9b13af8ce78e509c44269d0e07cedbb1d59"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.5G"
tar_bytes = 6941330944

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.8G"
zstd_bytes = 1861815580

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221004"
previous_tag = "2022-10-04"
previous_file = "fedora-mate_arm64_2022-10-04_15-03-rootfs.tar.zst"
previous_sha256 = "9e0b0cd8edd1942d360405a087ba31fe1ba5f6c2a7b373cc4df9bae509692eee"

current_version = "latest02"
current_date = "20221011"
old_file = "fedora-mate_arm64_2022-09-27_14-34-rootfs.tar.zst"
old_sha256 = "da99235c9146a97bdc3c4a40668e9de1b08ca002fcb0a4aed80b03f9513795c5"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-mate_arm64_2022-10-11_15-03-rootfs.tar.zst
# SHA256SUM=4a240f0f7e2eefbea85b8cce79e6e9b13af8ce78e509c44269d0e07cedbb1d59
# BUILD_DATE=20221011
# BUILD_TAG=2022-10-11
# STATUS=completed
# VERSION=latest02
# END_TIME=15:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-11
begin = 2022-10-11 12:51:03.717877544+00:00
start-sync_0 = 14:29:22
start-zstd = 14:35:58
start-sync_1 = 15:01:40
end-sync_1 = 15:03:50
end = 2022-10-11 15:03:50.624855795+00:00

[server]
repo = "cake233/fedora-mate-arm64"

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
