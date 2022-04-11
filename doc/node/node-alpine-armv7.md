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
tag = ["alpine", "2022-04-11", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "node-musl_armhf_2022-04-11_11-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7c19e6080245cb4b7094a92a727fab163a0f4af4f57369612dcb8d89db15cdc5"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "165M"
tar_bytes = 172688384

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "30M"
zstd_bytes = 31314056

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220328"
previous_tag = "2022-03-28"
previous_file = "node-musl_armhf_2022-03-28_11-04-rootfs.tar.zst"
previous_sha256 = "d75891fbb2578ebc59044661a786b2030f63325291e4aadafa5fd4bca03bb178"

current_version = "latest02"
current_date = "20220411"
old_file = "node-musl_armhf_2022-03-24_12-29-rootfs.tar.zst"
old_sha256 = "a44d7d05b20f454ad1970e767452c48e72f95ff1ab39f03d62f450d05b0173e4"
# edition 2021
# DISTRO_NAME=node_armhf
# ROOTFS_FILE=node-musl_armhf_2022-04-11_11-04-rootfs.tar.zst
# SHA256SUM=7c19e6080245cb4b7094a92a727fab163a0f4af4f57369612dcb8d89db15cdc5
# BUILD_DATE=20220411
# BUILD_TAG=2022-04-11
# STATUS=completed
# VERSION=latest02
# END_TIME=11:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-11
begin = 2022-04-11 11:02:35.573206474+00:00
start-sync_0 = 11:03:39
start-zstd = 11:03:46
start-sync_1 = 11:04:48
end-sync_1 = 11:04:55
end = 2022-04-11 11:04:55.532486560+00:00

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
node = 'v17.8.0'
yarn = '1.22.18'
npm = '8.5.5'
```
