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
tag = ["latest", "2022-04-11", "nightly"]
os = "ubuntu"
release = "focal"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "swift_amd64_2022-04-11_11-25.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4e5a953f509dd196e731d686c336cde1a8830da905be2fd2d200cff53164dcf8"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.6G"
tar_bytes = 2695810048

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "453M"
zstd_bytes = 474048305

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220328"
previous_tag = "2022-03-28"
previous_file = "swift_amd64_2022-03-28_11-24-rootfs.tar.zst"
previous_sha256 = "e940280994ca1f96d8c396ca8b7d32fd2b1696dc5f85020efa76ad668aec8315"

current_version = "latest01"
current_date = "20220411"
old_file = "swift_amd64_2022-03-24_12-51-rootfs.tar.zst"
old_sha256 = "5c9b9071215eba42e917c285586b4ed4a9c341296929b1666387faeece18d8c2"
# edition 2021
# DISTRO_NAME=swift_amd64
# ROOTFS_FILE=swift_amd64_2022-04-11_11-25-rootfs.tar.zst
# SHA256SUM=4e5a953f509dd196e731d686c336cde1a8830da905be2fd2d200cff53164dcf8
# BUILD_DATE=20220411
# BUILD_TAG=2022-04-11
# STATUS=completed
# VERSION=latest01
# END_TIME=11:25

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-11
begin = 2022-04-11 11:02:40.126943024+00:00
start-sync_0 = 11:04:54
start-zstd = 11:06:50
start-sync_1 = 11:25:05
end-sync_1 = 11:25:40
end = 2022-04-11 11:25:40.516480390+00:00

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
Swift version 5.7-dev (LLVM aac709978dda363, Swift 8c308d0ff137dde)
Target: x86_64-unknown-linux-gnu
'''
```
