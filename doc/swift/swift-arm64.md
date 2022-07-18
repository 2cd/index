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
tag = ["latest", "2022-07-18", "nightly"]
os = "ubuntu"
release = "focal"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_arm64_2022-07-18_12-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1a388df4cbf3a0bfb7e78d6af684805c9ed43f0a21a3dae33ae063b52f272968"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.5G"
tar_bytes = 2611991040

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "430M"
zstd_bytes = 450482028

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220704"
previous_tag = "2022-07-04"
previous_file = "swift_arm64_2022-07-04_12-30-rootfs.tar.zst"
previous_sha256 = "2d5e36addc0def79da8a531a3c2d016ee363ce27ff1503cf95135c8eb83105ce"

current_version = "latest02"
current_date = "20220718"
old_file = "swift_arm64_2022-06-20_12-31-rootfs.tar.zst"
old_sha256 = "cc9a6ac379fae987fc5cfc91bd83b6af7db8f1885226ff4bfcb24b6716f0a4f0"
# edition 2021
# DISTRO_NAME=swift_arm64
# ROOTFS_FILE=swift_arm64_2022-07-18_12-29-rootfs.tar.zst
# SHA256SUM=1a388df4cbf3a0bfb7e78d6af684805c9ed43f0a21a3dae33ae063b52f272968
# BUILD_DATE=20220718
# BUILD_TAG=2022-07-18
# STATUS=completed
# VERSION=latest02
# END_TIME=12:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-18
begin = 2022-07-18 12:02:30.582355848+00:00
start-sync_0 = 12:12:04
start-zstd = 12:13:42
start-sync_1 = 12:29:12
end-sync_1 = 12:29:46
end = 2022-07-18 12:29:46.229032346+00:00

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
Swift version 5.8-dev (LLVM bd78ff30de10748, Swift 33a987faca7b9d8)
Target: aarch64-unknown-linux-gnu
'''
```
