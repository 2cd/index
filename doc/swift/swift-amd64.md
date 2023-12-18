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
tag = ["latest", "2023-12-18", "nightly"]
os = "ubuntu"
release = "focal"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_amd64_2023-12-18_12-22.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a4c62faaae26aff5c697a49487bddc8673d8f41c243b6a749551266a52177b5c"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.1G"
tar_bytes = 3311013888

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "560M"
zstd_bytes = 586689318

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231120"
previous_tag = "2023-11-20"
previous_file = "swift_amd64_2023-11-20_12-21-rootfs.tar.zst"
previous_sha256 = "674129dd618228c9812ffe081793ea8d694cd9f0b408b6e1fa441a4d26bb6513"

current_version = "latest01"
current_date = "20231218"
old_file = "swift_amd64_2023-10-23_12-27-rootfs.tar.zst"
old_sha256 = "3501a5d0d67f07d6a5b76dcc49bd2af55edbb51a376c1c0563926bf9d673f507"
# edition 2021
# DISTRO_NAME=swift_amd64
# ROOTFS_FILE=swift_amd64_2023-12-18_12-22-rootfs.tar.zst
# SHA256SUM=a4c62faaae26aff5c697a49487bddc8673d8f41c243b6a749551266a52177b5c
# BUILD_DATE=20231218
# BUILD_TAG=2023-12-18
# STATUS=completed
# VERSION=latest01
# END_TIME=12:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-18
begin = 2023-12-18 12:02:33.717280648+00:00
start-sync_0 = 12:05:18
start-zstd = 12:07:00
start-sync_1 = 12:22:27
end-sync_1 = 12:22:56
end = 2023-12-18 12:22:56.426391043+00:00

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
Swift version 5.11-dev (LLVM 067380bceb10522, Swift 15a6c01a16e3465)
Target: x86_64-unknown-linux-gnu
'''
```
