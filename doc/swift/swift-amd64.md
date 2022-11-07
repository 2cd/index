# swift-amd64

## Example

```sh
TMP="/tmp/hello"
mkdir -p "$TMP"

docker run \
    -t \
    --rm \
    -v "$TMP":/app \
    -w /app \
    cake233/swift-amd64 \
    swift package init --type executable

docker run \
    -t \
    --rm \
    -v "$TMP":/app \
    -w /app \
    cake233/swift-amd64 \
    swift run --verbose
```

## How to exec shell?

```sh
docker run \
    -it \
    --security-opt seccomp=unconfined \
    --name swift-amd64 \
    cake233/swift-amd64
```


```sh
docker exec -it swift-amd64 bash
```


## swift-amd64.toml

```toml
[main]
name = "swift"
tag = ["latest", "2022-11-07", "nightly"]
os = "ubuntu"
release = "focal"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_amd64_2022-11-07_12-24.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f3e40ccd1277d3d9060ecdcddba0fa08f66037c946dd538b3eb529840d224e46"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.7G"
tar_bytes = 2803636736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "479M"
zstd_bytes = 501658078

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221024"
previous_tag = "2022-10-24"
previous_file = "swift_amd64_2022-10-24_12-31-rootfs.tar.zst"
previous_sha256 = "a0936c8fb7f128b6327001b6a2489208d44c9e8a51732a24c369d87c54bb353e"

current_version = "latest02"
current_date = "20221107"
old_file = "swift_amd64_2022-10-10_12-28-rootfs.tar.zst"
old_sha256 = "46dc87471e75793c08d7b5e88a2f1e142e88654893fa1931f24dea3c37e49d3d"
# edition 2021
# DISTRO_NAME=swift_amd64
# ROOTFS_FILE=swift_amd64_2022-11-07_12-24-rootfs.tar.zst
# SHA256SUM=f3e40ccd1277d3d9060ecdcddba0fa08f66037c946dd538b3eb529840d224e46
# BUILD_DATE=20221107
# BUILD_TAG=2022-11-07
# STATUS=completed
# VERSION=latest02
# END_TIME=12:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-07
begin = 2022-11-07 12:02:29.640884626+00:00
start-sync_0 = 12:05:08
start-zstd = 12:07:08
start-sync_1 = 12:23:56
end-sync_1 = 12:24:28
end = 2022-11-07 12:24:29.003869017+00:00

[server]
repo = "cake233/swift-amd64"

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
Swift version 5.8-dev (LLVM 1299cdab04e4506, Swift 56665d5ce9f6420)
Target: x86_64-unknown-linux-gnu
'''
```
