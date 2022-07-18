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
tag = ["alpine", "2022-07-18", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_armhf_2022-07-18_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "48133a5c25ab01736c0d70263c9057fa0943762cbeb11df027045c74b5254240"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "170M"
tar_bytes = 177842176

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 32344288

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220704"
previous_tag = "2022-07-04"
previous_file = "node-musl_armhf_2022-07-04_12-04-rootfs.tar.zst"
previous_sha256 = "4a6deb223b458c0445752179b94d6dd3e5065cdc08001b535a381ed40fa3fad5"

current_version = "latest01"
current_date = "20220718"
old_file = "node-musl_armhf_2022-06-20_12-04-rootfs.tar.zst"
old_sha256 = "32c7d863d7ae9f7453a1d5c44b374ad6352dcf2337591a65ddfdb87b3c8be92f"
# edition 2021
# DISTRO_NAME=node_armhf
# ROOTFS_FILE=node-musl_armhf_2022-07-18_12-04-rootfs.tar.zst
# SHA256SUM=48133a5c25ab01736c0d70263c9057fa0943762cbeb11df027045c74b5254240
# BUILD_DATE=20220718
# BUILD_TAG=2022-07-18
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-18
begin = 2022-07-18 12:02:30.117736862+00:00
start-sync_0 = 12:03:35
start-zstd = 12:03:45
start-sync_1 = 12:04:40
end-sync_1 = 12:04:50
end = 2022-07-18 12:04:50.929529638+00:00

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
node = 'v18.6.0'
yarn = '1.22.19'
npm = '8.13.2'
```
