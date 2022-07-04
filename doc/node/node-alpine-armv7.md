# node-alpine-armv7

## How to run it?

```sh
docker run \
    -it \
    --name node-alpine-armv7 \
    cake233/node-alpine-armv7
```

## How to exec shell?

```sh
docker exec -it node-alpine-armv7 bash
```

## node-alpine-armv7.toml

```toml
[main]
name = "node"
tag = ["alpine", "2022-07-04", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_armhf_2022-07-04_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4a6deb223b458c0445752179b94d6dd3e5065cdc08001b535a381ed40fa3fad5"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "170M"
tar_bytes = 177715712

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 32332646

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220620"
previous_tag = "2022-06-20"
previous_file = "node-musl_armhf_2022-06-20_12-04-rootfs.tar.zst"
previous_sha256 = "32c7d863d7ae9f7453a1d5c44b374ad6352dcf2337591a65ddfdb87b3c8be92f"

current_version = "latest02"
current_date = "20220704"
old_file = "node-musl_armhf_2022-06-06_12-04-rootfs.tar.zst"
old_sha256 = "8a5b5f01af1c1e09db8437b55a306ae4a7d1e99f8729990dc19bac80b33a4748"
# edition 2021
# DISTRO_NAME=node_armhf
# ROOTFS_FILE=node-musl_armhf_2022-07-04_12-04-rootfs.tar.zst
# SHA256SUM=4a6deb223b458c0445752179b94d6dd3e5065cdc08001b535a381ed40fa3fad5
# BUILD_DATE=20220704
# BUILD_TAG=2022-07-04
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-04
begin = 2022-07-04 12:02:35.116692455+00:00
start-sync_0 = 12:03:41
start-zstd = 12:03:50
start-sync_1 = 12:04:43
end-sync_1 = 12:04:49
end = 2022-07-04 12:04:49.265244058+00:00

[server]
repo = "cake233/node-alpine-armv7"

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (armhf) Version 1.2.3'
node = 'v18.4.0'
yarn = '1.22.19'
npm = '8.12.1'
```
