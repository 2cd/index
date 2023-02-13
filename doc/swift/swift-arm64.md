# swift-arm64

## Example

```sh
TMP="/tmp/hello"
mkdir -p "$TMP"

docker run \
    -t \
    --rm \
    -v "$TMP":/app \
    -w /app \
    cake233/swift-arm64 \
    swift package init --type executable

docker run \
    -t \
    --rm \
    -v "$TMP":/app \
    -w /app \
    cake233/swift-arm64 \
    swift run --verbose
```

## How to exec shell?

```sh
docker run \
    -it \
    --security-opt seccomp=unconfined \
    --name swift-arm64 \
    cake233/swift-arm64
```


```sh
docker exec -it swift-arm64 bash
```


## swift-arm64.toml

```toml
[main]
name = "swift"
tag = ["latest", "2023-02-13", "nightly"]
os = "ubuntu"
release = "focal"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_arm64_2023-02-13_12-39.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "05da87501ff5980dbaca95573f88e2f4d13f57e9480ca8672cfda820c5ab9d77"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.5G"
tar_bytes = 2645879808

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "436M"
zstd_bytes = 457165068

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230130"
previous_tag = "2023-01-30"
previous_file = "swift_arm64_2023-01-30_12-28-rootfs.tar.zst"
previous_sha256 = "b7ce64c32cc92d1b2655793bba435c98f422d1d11964c652de6b254c4d79569f"

current_version = "latest01"
current_date = "20230213"
old_file = "swift_arm64_2023-01-16_12-28-rootfs.tar.zst"
old_sha256 = "2ed30a4836ab117ed83c736ff3f6127b630e4298cb97618e4ae4d380770f9579"
# edition 2021
# DISTRO_NAME=swift_arm64
# ROOTFS_FILE=swift_arm64_2023-02-13_12-39-rootfs.tar.zst
# SHA256SUM=05da87501ff5980dbaca95573f88e2f4d13f57e9480ca8672cfda820c5ab9d77
# BUILD_DATE=20230213
# BUILD_TAG=2023-02-13
# STATUS=completed
# VERSION=latest01
# END_TIME=12:39

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-13
begin = 2023-02-13 12:04:16.700391098+00:00
start-sync_0 = 12:17:01
start-zstd = 12:19:04
start-sync_1 = 12:38:41
end-sync_1 = 12:39:22
end = 2023-02-13 12:39:22.916871169+00:00

[server]
repo = "cake233/swift-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.31-0ubuntu9.9) 2.31'
git = 'git version 2.25.1'
swift = '''
Swift version 5.9-dev (LLVM 50ed2bf09779f5f, Swift ea1d0a3a3a6971a)
Target: aarch64-unknown-linux-gnu
'''
```
