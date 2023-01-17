# ubuntu-mate-arm64

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
    --name ubuntu-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-mate-arm64 zsh
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

## ubuntu-mate-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["mate", "2023-01-17", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-mate_arm64_2023-01-17_00-52.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "94db9c2247d9b8fd4526958efb362ec1f01226c216a951258fbe29a6a5066e9b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.3G"
tar_bytes = 4566313472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1227017928

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230110"
previous_tag = "2023-01-10"
previous_file = "ubuntu-mate_arm64_2023-01-10_00-51-rootfs.tar.zst"
previous_sha256 = "899a6fe57bc67523c7d4d9f4c5d5273460482f5db76a09c65616f0266ce23ec8"

current_version = "latest01"
current_date = "20230117"
old_file = "ubuntu-mate_arm64_2023-01-03_01-13-rootfs.tar.zst"
old_sha256 = "426562692998835ff9d8ba368a198c94a788b96d11fbe90b5d09ef03d9887bb9"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-mate_arm64_2023-01-17_00-52-rootfs.tar.zst
# SHA256SUM=94db9c2247d9b8fd4526958efb362ec1f01226c216a951258fbe29a6a5066e9b
# BUILD_DATE=20230117
# BUILD_TAG=2023-01-17
# STATUS=completed
# VERSION=latest01
# END_TIME=00:52

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-17
begin = 2023-01-17 00:02:58.517668620+00:00
start-sync_0 = 00:32:44
start-zstd = 00:36:24
start-sync_1 = 00:51:37
end-sync_1 = 00:52:47
end = 2023-01-17 00:52:47.165878805+00:00

[server]
repo = "cake233/ubuntu-mate-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
