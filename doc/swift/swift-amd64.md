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
tag = ["latest", "2024-01-08", "nightly"]
os = "ubuntu"
release = "focal"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_amd64_2024-01-08_12-23.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4dc89af74a6ac98f94f75f4b8b1bc141529f54a58a243641fc07d7b8e934ac1a"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.2G"
tar_bytes = 3404220416

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "564M"
zstd_bytes = 590801689

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20240108"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=swift_amd64
# ROOTFS_FILE=swift_amd64_2024-01-08_12-23-rootfs.tar.zst
# SHA256SUM=4dc89af74a6ac98f94f75f4b8b1bc141529f54a58a243641fc07d7b8e934ac1a
# BUILD_DATE=20240108
# BUILD_TAG=2024-01-08
# STATUS=completed
# VERSION=latest01
# END_TIME=12:23

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-08
begin = 2024-01-08 12:02:32.512271046+00:00
start-sync_0 = 12:04:26
start-zstd = 12:06:10
start-sync_1 = 12:23:05
end-sync_1 = 12:23:33
end = 2024-01-08 12:23:33.866571669+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.31-0ubuntu9.14) 2.31'
git = 'git version 2.25.1'
swift = '''
Swift version 5.11-dev (LLVM afcd9c27bd73209, Swift b1a8ad8562228f0)
Target: x86_64-unknown-linux-gnu
'''
```
