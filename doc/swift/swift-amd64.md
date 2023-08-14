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
tag = ["latest", "2023-08-14", "nightly"]
os = "ubuntu"
release = "focal"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_amd64_2023-08-14_12-31.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "67cbc052e282c9f826bf3a0ab0397bb0c3ab78f12e34ced6df7b7b1c89d8ffdf"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.8G"
tar_bytes = 2941163520

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "509M"
zstd_bytes = 533625624

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230731"
previous_tag = "2023-07-31"
previous_file = "swift_amd64_2023-07-31_12-31-rootfs.tar.zst"
previous_sha256 = "be866250ae7698f84825122f994974c8f6ceace2e326f2eae04dc3b3635d47e3"

current_version = "latest01"
current_date = "20230814"
old_file = "swift_amd64_2023-07-17_12-25-rootfs.tar.zst"
old_sha256 = "93002acd193fc2a3a30e880c677f55df6d67891547b8c784b069591826f1d6a3"
# edition 2021
# DISTRO_NAME=swift_amd64
# ROOTFS_FILE=swift_amd64_2023-08-14_12-31-rootfs.tar.zst
# SHA256SUM=67cbc052e282c9f826bf3a0ab0397bb0c3ab78f12e34ced6df7b7b1c89d8ffdf
# BUILD_DATE=20230814
# BUILD_TAG=2023-08-14
# STATUS=completed
# VERSION=latest01
# END_TIME=12:31

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-14
begin = 2023-08-14 12:02:40.883704126+00:00
start-sync_0 = 12:07:04
start-zstd = 12:09:33
start-sync_1 = 12:30:56
end-sync_1 = 12:31:45
end = 2023-08-14 12:31:46.033330158+00:00

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
Swift version 5.9-dev (LLVM fd38736063c15cd, Swift a533c63d783f5b8)
Target: x86_64-unknown-linux-gnu
'''
```
