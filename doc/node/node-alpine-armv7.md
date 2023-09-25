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
tag = ["alpine", "2022-10-10", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_armhf_2022-10-10_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b12f6738ed2a74200c3078418a51c017c24b0a94f3a742ff79e09ed30adc3871"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "163M"
tar_bytes = 170027520

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 32502155

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220926"
previous_tag = "2022-09-26"
previous_file = "node-musl_armhf_2022-09-26_12-05-rootfs.tar.zst"
previous_sha256 = "81449395e8348de73c471f6e0af7d5b2b3db1d9602e8b1b7ec1b7fe10bb76ddc"

current_version = "latest01"
current_date = "20221010"
old_file = "node-musl_armhf_2022-09-12_12-04-rootfs.tar.zst"
old_sha256 = "71c4d4d0550a11a3b435941392f9c48a2dafd1c46e4d00043b04cc38182e7644"
# edition 2021
# DISTRO_NAME=node_armhf
# ROOTFS_FILE=node-musl_armhf_2022-10-10_12-04-rootfs.tar.zst
# SHA256SUM=b12f6738ed2a74200c3078418a51c017c24b0a94f3a742ff79e09ed30adc3871
# BUILD_DATE=20221010
# BUILD_TAG=2022-10-10
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-10
begin = 2022-10-10 12:02:29.197207953+00:00
start-sync_0 = 12:03:38
start-zstd = 12:03:48
start-sync_1 = 12:04:46
end-sync_1 = 12:04:55
end = 2022-10-10 12:04:55.238330554+00:00

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
node = 'v18.10.0'
yarn = '1.22.19'
npm = '8.19.2'
```