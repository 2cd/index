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
tag = ["latest", "2022-03-28", "nightly"]
os = "ubuntu"
release = "focal"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "swift_amd64_2022-03-28_11-24.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "e940280994ca1f96d8c396ca8b7d32fd2b1696dc5f85020efa76ad668aec8315"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.6G"
tar_bytes = 2691680256

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "452M"
zstd_bytes = 473599198

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220324"
previous_tag = "2022-03-24"
previous_file = "swift_amd64_2022-03-24_12-51-rootfs.tar.zst"
previous_sha256 = "5c9b9071215eba42e917c285586b4ed4a9c341296929b1666387faeece18d8c2"

current_version = "latest02"
current_date = "20220328"
old_file = "swift_amd64_2022-03-16_04-48-rootfs.tar.zst"
old_sha256 = "1281758167203552ab148f3aa460cf48a69eabe6a5ba6cd2205a6a899cfaa763"
# edition 2021
# DISTRO_NAME=swift_amd64
# ROOTFS_FILE=swift_amd64_2022-03-28_11-24-rootfs.tar.zst
# SHA256SUM=e940280994ca1f96d8c396ca8b7d32fd2b1696dc5f85020efa76ad668aec8315
# BUILD_DATE=20220328
# BUILD_TAG=2022-03-28
# STATUS=completed
# VERSION=latest02
# END_TIME=11:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-28
begin = 2022-03-28 11:02:27.562669710+00:00
start-sync_0 = 11:04:28
start-zstd = 11:06:23
start-sync_1 = 11:24:13
end-sync_1 = 11:24:45
end = 2022-03-28 11:24:45.893708341+00:00

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (Ubuntu GLIBC 2.31-0ubuntu9.7) 2.31'
git = 'git version 2.25.1'
swift = '''
Swift version 5.7-dev (LLVM a70fc75b0dfacb7, Swift 687beace5e0c77a)
Target: x86_64-unknown-linux-gnu
'''
```
