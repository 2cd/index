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
tag = ["alpine", "2022-05-23", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_armhf_2022-05-23_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "10458b72f9c6b2ff0deaa1f3125dab4c02ddaed9ab8f926d31dc2f9a29d81cc9"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "168M"
tar_bytes = 175556608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 32009471

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220509"
previous_tag = "2022-05-09"
previous_file = "node-musl_armhf_2022-05-09_12-04-rootfs.tar.zst"
previous_sha256 = "e407393e2bacf1fb64e4bf25cefb71304871cb3a4250f7da2a13786a4543f1ad"

current_version = "latest01"
current_date = "20220523"
old_file = "node-musl_armhf_2022-04-25_12-04-rootfs.tar.zst"
old_sha256 = "37bd5b93766ef227937d6e6cd71dcfdcebc7b8d2c2b99d91d9542700c68f2b83"
# edition 2021
# DISTRO_NAME=node_armhf
# ROOTFS_FILE=node-musl_armhf_2022-05-23_12-04-rootfs.tar.zst
# SHA256SUM=10458b72f9c6b2ff0deaa1f3125dab4c02ddaed9ab8f926d31dc2f9a29d81cc9
# BUILD_DATE=20220523
# BUILD_TAG=2022-05-23
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-23
begin = 2022-05-23 12:02:34.072558748+00:00
start-sync_0 = 12:03:25
start-zstd = 12:03:36
start-sync_1 = 12:04:26
end-sync_1 = 12:04:37
end = 2022-05-23 12:04:37.146042495+00:00

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
ldd = 'musl libc (armhf) Version 1.2.2'
node = 'v18.2.0'
yarn = '1.22.19'
npm = '8.9.0'
```
