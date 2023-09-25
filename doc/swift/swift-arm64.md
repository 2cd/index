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
tag = ["latest", "2023-09-25", "nightly"]
os = "ubuntu"
release = "focal"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_arm64_2023-09-25_12-37.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "cc8a05651744a19bbfeaee464d7ab6165162efb3f528c8e1b39061845b9b2ec8"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.8G"
tar_bytes = 3004480512

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "509M"
zstd_bytes = 532783968

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230911"
previous_tag = "2023-09-11"
previous_file = "swift_arm64_2023-09-11_12-37-rootfs.tar.zst"
previous_sha256 = "25cbd5b12be05a9229228e1d2d63adec1777771bf4efcea13e3ec1457e8987f6"

current_version = "latest01"
current_date = "20230925"
old_file = "swift_arm64_2023-08-28_12-31-rootfs.tar.zst"
old_sha256 = "a4defea44a340875c9b14f1589d3a55dc6fd8905701d8fb37eed71d316d2de8f"
# edition 2021
# DISTRO_NAME=swift_arm64
# ROOTFS_FILE=swift_arm64_2023-09-25_12-37-rootfs.tar.zst
# SHA256SUM=cc8a05651744a19bbfeaee464d7ab6165162efb3f528c8e1b39061845b9b2ec8
# BUILD_DATE=20230925
# BUILD_TAG=2023-09-25
# STATUS=completed
# VERSION=latest01
# END_TIME=12:37

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-25
begin = 2023-09-25 12:02:37.969511191+00:00
start-sync_0 = 12:14:25
start-zstd = 12:16:41
start-sync_1 = 12:36:47
end-sync_1 = 12:37:34
end = 2023-09-25 12:37:34.951857139+00:00

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
Swift version 5.11-dev (LLVM 69cd2190ea64502, Swift 8fa720d27ee0e0b)
Target: aarch64-unknown-linux-gnu
'''
```
