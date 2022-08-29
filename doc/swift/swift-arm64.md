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
tag = ["latest", "2022-08-29", "nightly"]
os = "ubuntu"
release = "focal"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_arm64_2022-08-29_12-35.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4d2812fcce3bcaf764b385de7302e64077419087f1e7acb8059647e413063dbb"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.5G"
tar_bytes = 2650305024

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "440M"
zstd_bytes = 460868483

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220815"
previous_tag = "2022-08-15"
previous_file = "swift_arm64_2022-08-15_12-37-rootfs.tar.zst"
previous_sha256 = "54806f50c1b22663d3222a2669a89b1e880c23496114cfb603e5ea7d2b5c8aaf"

current_version = "latest01"
current_date = "20220829"
old_file = "swift_arm64_2022-07-04_12-30-rootfs.tar.zst"
old_sha256 = "2d5e36addc0def79da8a531a3c2d016ee363ce27ff1503cf95135c8eb83105ce"
# edition 2021
# DISTRO_NAME=swift_arm64
# ROOTFS_FILE=swift_arm64_2022-08-29_12-35-rootfs.tar.zst
# SHA256SUM=4d2812fcce3bcaf764b385de7302e64077419087f1e7acb8059647e413063dbb
# BUILD_DATE=20220829
# BUILD_TAG=2022-08-29
# STATUS=completed
# VERSION=latest01
# END_TIME=12:35

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-29
begin = 2022-08-29 12:02:33.318359994+00:00
start-sync_0 = 12:15:03
start-zstd = 12:17:02
start-sync_1 = 12:35:09
end-sync_1 = 12:35:47
end = 2022-08-29 12:35:47.872468016+00:00

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
Swift version 5.8-dev (LLVM 0d85470fdf4efaa, Swift 730bf2403582f35)
Target: aarch64-unknown-linux-gnu
'''
```
