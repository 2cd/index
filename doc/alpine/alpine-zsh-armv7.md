# alpine-zsh-armv7

## How to run it?

```shell
docker run \
    -it \
    --name alpine-zsh-armv7 \
    cake233/alpine-zsh-armv7
```

## How to exec shell?

```shell
    docker exec -it alpine-zsh-armv7 zsh
```

## alpine-zsh-armv7.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2021-11-29"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "alpine-zsh_armhf_2021-11-29_18-06.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "1449ce18579e70127f0b3d2796fd6b1131cdd9a7726d12b1f0e09670bd5b2170"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "73M"
tar_bytes = 76036608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "25M"
zstd_bytes = 25912722

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211128"
last_tag = "2021-11-28"
last_file = "alpine-zsh-armv7_2021-11-28_20-55-rootfs.tar.zst"

current_version = "latest01"
current_date = "20211129"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-zsh_armhf_2021-11-29_18-06-rootfs.tar.zst
# BUILD_DATE=20211129
# BUILD_TAG=2021-11-29
# STATUS=completed
# VERSION=latest01
# END_TIME=18:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-29
begin = 2021-11-29 18:03:02.485256539+00:00
start-sync_0 = 18:04:35
start-zstd = 18:05:57
start-sync_1 = 18:06:21
end-sync_1 = 18:06:29
end = 2021-11-29 18:06:29.670674360+00:00

[server]
repo = "cake233/alpine-zsh-armv7"

[server.node1]
name = "cn"
current = false
last = true
split = false

[server.node2]
name = "us"
current = false
last = true
split = false
part = 12

[server.node3]
name = "global"
current = false
last = true
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "C.UTF-8"
```
