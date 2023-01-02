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
tag = ["alpine", "2023-01-02", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_arm64_2023-01-02_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b2946eebf9d6c5d0203d86f03b7fdcaf27ad9f965b7eada0e85081857c44544d"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "192M"
tar_bytes = 201310208

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "34M"
zstd_bytes = 34867455

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221219"
previous_tag = "2022-12-19"
previous_file = "node-musl_arm64_2022-12-19_12-06-rootfs.tar.zst"
previous_sha256 = "6e3c38b170f85aeb83f5596f354ea11353cd14a43adc25d2ddd0bd9d38ebc029"

current_version = "latest02"
current_date = "20230102"
old_file = "node-musl_arm64_2022-12-05_12-05-rootfs.tar.zst"
old_sha256 = "acf0fbcffcbfa0b7aaf7944d977b3c9dd01141bf4961d1d07a7645141048c2b5"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node-musl_arm64_2023-01-02_12-05-rootfs.tar.zst
# SHA256SUM=b2946eebf9d6c5d0203d86f03b7fdcaf27ad9f965b7eada0e85081857c44544d
# BUILD_DATE=20230102
# BUILD_TAG=2023-01-02
# STATUS=completed
# VERSION=latest02
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-02
begin = 2023-01-02 12:02:37.291319012+00:00
start-sync_0 = 12:04:01
start-zstd = 12:04:12
start-sync_1 = 12:05:29
end-sync_1 = 12:05:39
end = 2023-01-02 12:05:39.415898467+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.3'
node = 'v19.3.0'
yarn = '1.22.19'
npm = '9.2.0'
```
