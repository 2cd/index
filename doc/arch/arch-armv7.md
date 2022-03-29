# arch-armv7

## How to run it?

```sh
docker run \
    -it \
    --name arch-armv7 \
    cake233/arch-armv7
```

## How to exec shell?

```sh
docker exec -it arch-armv7 sh
```

## arch-armv7.toml

```toml
[main]
name = "arch"
tag = ["base", "2022-03-29"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "arch_armhf_2022-03-29_23-04.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "2c55d33ab49e4b2095f9f8ea1334b87a389435cabb3ad961d34161498648dddf"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "563M"
tar_bytes = 589499392

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "170M"
zstd_bytes = 177279869

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220329"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch_armhf_2022-03-29_23-04-rootfs.tar.zst
# SHA256SUM=2c55d33ab49e4b2095f9f8ea1334b87a389435cabb3ad961d34161498648dddf
# BUILD_DATE=20220329
# BUILD_TAG=2022-03-29
# STATUS=completed
# VERSION=latest01
# END_TIME=23:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-29
begin = 2022-03-29 23:02:24.457185814+00:00
start-sync_0 = 23:03:43
start-zstd = 23:04:21
start-sync_1 = 23:04:38
end-sync_1 = 23:04:53
end = 2022-03-29 23:04:53.521050801+00:00

[server]
repo = "cake233/arch-armv7"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = false
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
previous = false
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
