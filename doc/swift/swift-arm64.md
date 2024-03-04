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
tag = ["latest", "2024-03-04", "nightly"]
os = "ubuntu"
release = "focal"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_arm64_2024-03-04_12-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1e7563730c980d2897765cc8e8ec9df891ea2e2581a8e90c715f1580b026c03a"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.3G"
tar_bytes = 3521041408

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "562M"
zstd_bytes = 588469740

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231120"
previous_tag = "2023-11-20"
previous_file = "swift_arm64_2023-11-20_12-29-rootfs.tar.zst"
previous_sha256 = "f6f5dafe6e28c74b888b3fe6898633cb79ca16753f00f0096d3db992a3ce7184"

current_version = "latest01"
current_date = "20240304"
old_file = "swift_arm64_2023-10-23_12-39-rootfs.tar.zst"
old_sha256 = "7b32a2e960c3662b4f12bc9815a9884337ef42a475ed5141b158b9f7db205680"
# edition 2021
# DISTRO_NAME=swift_arm64
# ROOTFS_FILE=swift_arm64_2024-03-04_12-29-rootfs.tar.zst
# SHA256SUM=1e7563730c980d2897765cc8e8ec9df891ea2e2581a8e90c715f1580b026c03a
# BUILD_DATE=20240304
# BUILD_TAG=2024-03-04
# STATUS=completed
# VERSION=latest01
# END_TIME=12:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-03-04
begin = 2024-03-04 12:02:36.349013999+00:00
start-sync_0 = 12:10:54
start-zstd = 12:12:37
start-sync_1 = 12:28:50
end-sync_1 = 12:29:20
end = 2024-03-04 12:29:20.093842078+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.31-0ubuntu9.14) 2.31'
git = 'git version 2.25.1'
swift = '''
Swift version 6.0-dev (LLVM 0c7823cab15dec9, Swift 0cc05909334c6f7)
Target: aarch64-unknown-linux-gnu
'''
```
