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
tag = ["latest", "2022-03-15", "nightly"]
os = "ubuntu"
release = "focal"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "swift_amd64_2022-03-15_19-15.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "c6365ff763e6a2b7830c5fa6ea5d7ed0a92d57ebaa373a99e26df091bb1c4c92"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.5G"
tar_bytes = 2595660288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "510M"
zstd_bytes = 534388670

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220315"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=swift_amd64
# ROOTFS_FILE=swift_amd64_2022-03-15_19-15-rootfs.tar.zst
# SHA256SUM=c6365ff763e6a2b7830c5fa6ea5d7ed0a92d57ebaa373a99e26df091bb1c4c92
# BUILD_DATE=20220315
# BUILD_TAG=2022-03-15
# STATUS=completed
# VERSION=latest01
# END_TIME=19:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-15
begin = 2022-03-15 19:02:07.921152711+00:00
start-sync_0 = 19:03:30
start-zstd = 19:04:10
start-sync_1 = 19:14:32
end-sync_1 = 19:15:11
end = 2022-03-15 19:15:11.078389384+00:00

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
swift = '''
Swift version 5.6-dev (LLVM 62b900d3d0d5be9, Swift ce64fe8867792d4)
Target: x86_64-unknown-linux-gnu
'''

```
