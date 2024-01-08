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
tag = ["latest", "2024-01-08", "nightly"]
os = "ubuntu"
release = "focal"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_arm64_2024-01-08_12-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5664ede840a6360ada3d3e258e8609508de3e87024fc39c54bed2e0e6feae163"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.2G"
tar_bytes = 3366777344

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "542M"
zstd_bytes = 567742361

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
# DISTRO_NAME=swift_arm64
# ROOTFS_FILE=swift_arm64_2024-01-08_12-28-rootfs.tar.zst
# SHA256SUM=5664ede840a6360ada3d3e258e8609508de3e87024fc39c54bed2e0e6feae163
# BUILD_DATE=20240108
# BUILD_TAG=2024-01-08
# STATUS=completed
# VERSION=latest01
# END_TIME=12:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-08
begin = 2024-01-08 12:02:37.424459324+00:00
start-sync_0 = 12:10:03
start-zstd = 12:11:40
start-sync_1 = 12:28:26
end-sync_1 = 12:28:57
end = 2024-01-08 12:28:57.908736940+00:00

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
Swift version 5.11-dev (LLVM afcd9c27bd73209, Swift b1a8ad8562228f0)
Target: aarch64-unknown-linux-gnu
'''
```
