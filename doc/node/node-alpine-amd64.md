# node-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name node-alpine-amd64 \
    cake233/node-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it node-alpine-amd64 bash
```

## node-alpine-amd64.toml

```toml
[main]
name = "node"
tag = ["alpine", "2022-07-18", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_amd64_2022-07-18_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "45bd3f11683cc28310a0904abc0bcdc9923a03e114a61cab3a2500a1118ee7f3"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "186M"
tar_bytes = 194305024

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "33M"
zstd_bytes = 33941806

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220704"
previous_tag = "2022-07-04"
previous_file = "node-musl_amd64_2022-07-04_12-04-rootfs.tar.zst"
previous_sha256 = "c1527f2e5930ef6dbbc94cc9744f5229b5097fc82a53698b02b5c3c6b57a55a1"

current_version = "latest01"
current_date = "20220718"
old_file = "node-musl_amd64_2022-06-20_12-05-rootfs.tar.zst"
old_sha256 = "e528cb318a3a369a513a8e8436e62ac48f716853256b61eecc04840248b7ee6e"
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node-musl_amd64_2022-07-18_12-04-rootfs.tar.zst
# SHA256SUM=45bd3f11683cc28310a0904abc0bcdc9923a03e114a61cab3a2500a1118ee7f3
# BUILD_DATE=20220718
# BUILD_TAG=2022-07-18
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-18
begin = 2022-07-18 12:02:29.837818497+00:00
start-sync_0 = 12:03:18
start-zstd = 12:03:29
start-sync_1 = 12:04:29
end-sync_1 = 12:04:38
end = 2022-07-18 12:04:38.339391649+00:00

[server]
repo = "cake233/node-alpine-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.3'
node = 'v18.6.0'
yarn = '1.22.19'
npm = '8.13.2'
```
