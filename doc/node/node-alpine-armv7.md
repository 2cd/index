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
tag = ["alpine", "2022-09-12", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_armhf_2022-09-12_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "71c4d4d0550a11a3b435941392f9c48a2dafd1c46e4d00043b04cc38182e7644"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "163M"
tar_bytes = 169915392

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 32494510

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220829"
previous_tag = "2022-08-29"
previous_file = "node-musl_armhf_2022-08-29_12-05-rootfs.tar.zst"
previous_sha256 = "3a5e485f170b37ac6444db1d1388b8ebf389225943946a54dd52d2c12781e842"

current_version = "latest01"
current_date = "20220912"
old_file = "node-musl_armhf_2022-08-15_12-05-rootfs.tar.zst"
old_sha256 = "2678015b91b8b25c1e6e25fc5882de8d5c4c1a0bf63df4e2313a306b81230658"
# edition 2021
# DISTRO_NAME=node_armhf
# ROOTFS_FILE=node-musl_armhf_2022-09-12_12-04-rootfs.tar.zst
# SHA256SUM=71c4d4d0550a11a3b435941392f9c48a2dafd1c46e4d00043b04cc38182e7644
# BUILD_DATE=20220912
# BUILD_TAG=2022-09-12
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-12
begin = 2022-09-12 12:02:27.555935501+00:00
start-sync_0 = 12:03:34
start-zstd = 12:03:40
start-sync_1 = 12:04:33
end-sync_1 = 12:04:39
end = 2022-09-12 12:04:39.722463726+00:00

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
node = 'v18.8.0'
yarn = '1.22.19'
npm = '8.18.0'
```
