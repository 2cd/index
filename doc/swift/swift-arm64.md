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
tag = ["latest", "2024-02-19", "nightly"]
os = "ubuntu"
release = "focal"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_arm64_2024-02-19_12-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "44bcc34afcb96a5be4894f381ff54c71e2153b37d7c0d7d6dc8fdd73468fb060"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.3G"
tar_bytes = 3530035200

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "561M"
zstd_bytes = 587443167

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20240219"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=swift_arm64
# ROOTFS_FILE=swift_arm64_2024-02-19_12-29-rootfs.tar.zst
# SHA256SUM=44bcc34afcb96a5be4894f381ff54c71e2153b37d7c0d7d6dc8fdd73468fb060
# BUILD_DATE=20240219
# BUILD_TAG=2024-02-19
# STATUS=completed
# VERSION=latest01
# END_TIME=12:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-19
begin = 2024-02-19 12:02:40.529389761+00:00
start-sync_0 = 12:11:22
start-zstd = 12:13:06
start-sync_1 = 12:28:46
end-sync_1 = 12:29:18
end = 2024-02-19 12:29:18.047286335+00:00

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
Swift version 5.11-dev (LLVM 48dba337c6a2104, Swift 823db1fc0821481)
Target: aarch64-unknown-linux-gnu
'''
```
