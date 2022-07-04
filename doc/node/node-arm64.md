# node-arm64

## How to run it?

```sh
docker run \
    -it \
    --name node-arm64 \
    cake233/node-arm64
```

## How to exec shell?

```sh
docker exec -it node-arm64 bash
```

## node-arm64.toml

```toml
[main]
name = "node"
tag = ["latest", "2022-07-04"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_arm64_2022-07-04_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a918efefb51f14a9f5f67fad6023886253dde7e93e653f645f296b6e8d75b012"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "951M"
tar_bytes = 996890112

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "197M"
zstd_bytes = 206538928

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220620"
previous_tag = "2022-06-20"
previous_file = "node_arm64_2022-06-20_12-10-rootfs.tar.zst"
previous_sha256 = "8c572bc5c3059ea0e0e9c77b0ba664322e2d2160e7ec8aaa0558ab50b1423b71"

current_version = "latest01"
current_date = "20220704"
old_file = "node_arm64_2022-06-06_12-11-rootfs.tar.zst"
old_sha256 = "49390eb9fc32ee89007e05166b0381e8c4947c5daf61ea32fef32e49154c0ef1"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node_arm64_2022-07-04_12-12-rootfs.tar.zst
# SHA256SUM=a918efefb51f14a9f5f67fad6023886253dde7e93e653f645f296b6e8d75b012
# BUILD_DATE=20220704
# BUILD_TAG=2022-07-04
# STATUS=completed
# VERSION=latest01
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-04
begin = 2022-07-04 12:02:32.240020592+00:00
start-sync_0 = 12:06:26
start-zstd = 12:06:46
start-sync_1 = 12:12:20
end-sync_1 = 12:12:38
end = 2022-07-04 12:12:38.857694810+00:00

[server]
repo = "cake233/node-arm64"

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
node = 'v18.4.0'
yarn = '1.22.19'
npm = '8.12.1'
```
