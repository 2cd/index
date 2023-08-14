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
tag = ["latest", "2023-08-14", "nightly"]
os = "ubuntu"
release = "focal"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_arm64_2023-08-14_12-32.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b98aa44bfe9816dc67ff904812229a5ebb39724d08cf08bb1c0a8f597b2d0e55"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.7G"
tar_bytes = 2799959040

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "471M"
zstd_bytes = 493178791

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230731"
previous_tag = "2023-07-31"
previous_file = "swift_arm64_2023-07-31_12-30-rootfs.tar.zst"
previous_sha256 = "57695814e697ab16cf79167a3cd294fe958e8ebccb3e13621cbaae802f479308"

current_version = "latest01"
current_date = "20230814"
old_file = "swift_arm64_2023-07-17_12-31-rootfs.tar.zst"
old_sha256 = "9f7d2f3e60d770195cc27b0f20ef46db580b734afbca19edffa30b9a1bc85c4b"
# edition 2021
# DISTRO_NAME=swift_arm64
# ROOTFS_FILE=swift_arm64_2023-08-14_12-32-rootfs.tar.zst
# SHA256SUM=b98aa44bfe9816dc67ff904812229a5ebb39724d08cf08bb1c0a8f597b2d0e55
# BUILD_DATE=20230814
# BUILD_TAG=2023-08-14
# STATUS=completed
# VERSION=latest01
# END_TIME=12:32

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-14
begin = 2023-08-14 12:02:38.130663086+00:00
start-sync_0 = 12:12:51
start-zstd = 12:14:33
start-sync_1 = 12:31:30
end-sync_1 = 12:32:20
end = 2023-08-14 12:32:20.580901244+00:00

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
Swift version 5.9-dev (LLVM fd38736063c15cd, Swift a533c63d783f5b8)
Target: aarch64-unknown-linux-gnu
'''
```
