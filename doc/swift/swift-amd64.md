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
tag = ["latest", "2022-09-12", "nightly"]
os = "ubuntu"
release = "focal"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_amd64_2022-09-12_12-24.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5e6b325305845c9fb7a483615edee8af2a743233e4d638c4050d79ab31f50f6d"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.6G"
tar_bytes = 2787246080

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "481M"
zstd_bytes = 503838155

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220829"
previous_tag = "2022-08-29"
previous_file = "swift_amd64_2022-08-29_12-28-rootfs.tar.zst"
previous_sha256 = "35a3fc167ac313c28a3a5e70cdfb5465bd4ac4300dfa0c7437c9d8c433e080bb"

current_version = "latest02"
current_date = "20220912"
old_file = "swift_amd64_2022-08-15_12-26-rootfs.tar.zst"
old_sha256 = "19a2cb1a25a348c631b174f6055c65acfcfd2e6a5d2a3b08c9e44a0be5e1ef75"
# edition 2021
# DISTRO_NAME=swift_amd64
# ROOTFS_FILE=swift_amd64_2022-09-12_12-24-rootfs.tar.zst
# SHA256SUM=5e6b325305845c9fb7a483615edee8af2a743233e4d638c4050d79ab31f50f6d
# BUILD_DATE=20220912
# BUILD_TAG=2022-09-12
# STATUS=completed
# VERSION=latest02
# END_TIME=12:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-12
begin = 2022-09-12 12:02:28.072856691+00:00
start-sync_0 = 12:05:17
start-zstd = 12:07:10
start-sync_1 = 12:24:03
end-sync_1 = 12:24:38
end = 2022-09-12 12:24:38.700039536+00:00

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
Swift version 5.8-dev (LLVM 6ad20b8df5a475e, Swift 005c9f340315004)
Target: x86_64-unknown-linux-gnu
'''
```
