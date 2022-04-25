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
tag = ["alpine", "2022-04-25", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "node-musl_armhf_2022-04-25_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "37bd5b93766ef227937d6e6cd71dcfdcebc7b8d2c2b99d91d9542700c68f2b83"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "168M"
tar_bytes = 175478784

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 31958659

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220411"
previous_tag = "2022-04-11"
previous_file = "node-musl_armhf_2022-04-11_11-04-rootfs.tar.zst"
previous_sha256 = "7c19e6080245cb4b7094a92a727fab163a0f4af4f57369612dcb8d89db15cdc5"

current_version = "latest01"
current_date = "20220425"
old_file = "node-musl_armhf_2022-03-28_11-04-rootfs.tar.zst"
old_sha256 = "d75891fbb2578ebc59044661a786b2030f63325291e4aadafa5fd4bca03bb178"
# edition 2021
# DISTRO_NAME=node_armhf
# ROOTFS_FILE=node-musl_armhf_2022-04-25_12-04-rootfs.tar.zst
# SHA256SUM=37bd5b93766ef227937d6e6cd71dcfdcebc7b8d2c2b99d91d9542700c68f2b83
# BUILD_DATE=20220425
# BUILD_TAG=2022-04-25
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-25
begin = 2022-04-25 12:02:31.416344238+00:00
start-sync_0 = 12:03:30
start-zstd = 12:03:37
start-sync_1 = 12:04:42
end-sync_1 = 12:04:49
end = 2022-04-25 12:04:49.621184989+00:00

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (armhf) Version 1.2.2'
node = 'v18.0.0'
yarn = '1.22.18'
npm = '8.6.0'
```
