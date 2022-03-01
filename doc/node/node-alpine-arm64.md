# node-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name node-alpine-arm64 \
    cake233/node-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it node-alpine-arm64 bash
```

## node-alpine-arm64.toml

```toml
[main]
name = "node"
tag = ["alpine", "2022-03-01", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "node-musl_arm64_2022-03-01_18-55.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "881964f89b2d3e27cb4f1c1a7371f2f6287ce31f7ca9b6ad9be74f66e72d8826"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "179M"
tar_bytes = 186681856

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "33M"
zstd_bytes = 34591980

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220214"
previous_tag = "2022-02-14"
previous_file = "node-musl_arm64_2022-02-14_12-03-rootfs.tar.zst"
previous_sha256 = "1baf0c9ad5f969b75d0b8903b18b5e0472154a390974315a086f12082fc64def"

current_version = "latest01"
current_date = "20220301"
old_file = "node-musl_arm64_2022-01-31_12-04-rootfs.tar.zst"
old_sha256 = "4a378068652a0e198b59ab932a67c9f2275bdc1c65c510224fb224d7234a8553"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node-musl_arm64_2022-03-01_18-55-rootfs.tar.zst
# SHA256SUM=881964f89b2d3e27cb4f1c1a7371f2f6287ce31f7ca9b6ad9be74f66e72d8826
# BUILD_DATE=20220301
# BUILD_TAG=2022-03-01
# STATUS=completed
# VERSION=latest01
# END_TIME=18:55

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-01
begin = 2022-03-01 18:53:55.128582590+00:00
start-sync_0 = 18:54:44
start-zstd = 18:54:55
start-sync_1 = 18:55:19
end-sync_1 = 18:55:28
end = 2022-03-01 18:55:28.602814625+00:00

[server]
repo = "cake233/node-alpine-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.2'
node = 'v17.6.0'
yarn = '1.22.17'
npm = '8.5.1'
```
