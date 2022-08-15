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
tag = ["latest", "2022-08-15", "nightly"]
os = "ubuntu"
release = "focal"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_amd64_2022-08-15_12-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "19a2cb1a25a348c631b174f6055c65acfcfd2e6a5d2a3b08c9e44a0be5e1ef75"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.6G"
tar_bytes = 2746737152

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "471M"
zstd_bytes = 493200115

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220704"
previous_tag = "2022-07-04"
previous_file = "swift_amd64_2022-07-04_12-26-rootfs.tar.zst"
previous_sha256 = "d2c7cbd75002d9d7877fbd9ef45f15e8d4ed4e5bdac2c07937adf65777a679eb"

current_version = "latest02"
current_date = "20220815"
old_file = "swift_amd64_2022-06-20_12-25-rootfs.tar.zst"
old_sha256 = "13875b76311ea5d19119f25757db6df523a663beed9837b34f9c56f22c814946"
# edition 2021
# DISTRO_NAME=swift_amd64
# ROOTFS_FILE=swift_amd64_2022-08-15_12-26-rootfs.tar.zst
# SHA256SUM=19a2cb1a25a348c631b174f6055c65acfcfd2e6a5d2a3b08c9e44a0be5e1ef75
# BUILD_DATE=20220815
# BUILD_TAG=2022-08-15
# STATUS=completed
# VERSION=latest02
# END_TIME=12:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-15
begin = 2022-08-15 12:02:28.675211317+00:00
start-sync_0 = 12:05:15
start-zstd = 12:07:11
start-sync_1 = 12:26:15
end-sync_1 = 12:26:51
end = 2022-08-15 12:26:51.469663633+00:00

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
Swift version 5.8-dev (LLVM 1e58bcc5bf50ea9, Swift 42135e27c4cf80e)
Target: x86_64-unknown-linux-gnu
'''
```
