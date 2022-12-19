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
tag = ["latest", "2022-12-19", "nightly"]
os = "ubuntu"
release = "focal"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_arm64_2022-12-19_12-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "56cad8d0b43b612e396710471a6b1b0a3528fa29225807b2f69717d1945304d7"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.5G"
tar_bytes = 2603529728

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "436M"
zstd_bytes = 456562689

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221205"
previous_tag = "2022-12-05"
previous_file = "swift_arm64_2022-12-05_12-30-rootfs.tar.zst"
previous_sha256 = "4dff5e9b056750ec9990654976fa43d4829195465bb680e9cef1759c9494aae9"

current_version = "latest01"
current_date = "20221219"
old_file = "swift_arm64_2022-11-21_12-34-rootfs.tar.zst"
old_sha256 = "81dccdd4db2a8e29697b1d36263d73818a99ca7352d7d38f9d2f4fab656f195e"
# edition 2021
# DISTRO_NAME=swift_arm64
# ROOTFS_FILE=swift_arm64_2022-12-19_12-29-rootfs.tar.zst
# SHA256SUM=56cad8d0b43b612e396710471a6b1b0a3528fa29225807b2f69717d1945304d7
# BUILD_DATE=20221219
# BUILD_TAG=2022-12-19
# STATUS=completed
# VERSION=latest01
# END_TIME=12:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-19
begin = 2022-12-19 12:02:32.666552932+00:00
start-sync_0 = 12:12:13
start-zstd = 12:13:52
start-sync_1 = 12:29:02
end-sync_1 = 12:29:32
end = 2022-12-19 12:29:32.634527038+00:00

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
Swift version 5.8-dev (LLVM a9b2e25093f61e9, Swift b206c76eff14170)
Target: aarch64-unknown-linux-gnu
'''
```
