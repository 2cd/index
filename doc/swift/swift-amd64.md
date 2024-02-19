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
tag = ["latest", "2024-02-19", "nightly"]
os = "ubuntu"
release = "focal"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_amd64_2024-02-19_12-25.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3fbc4107547fbec09d27caeee58a266fd4c5d0b5f6f9cab54db59139ae8c83ff"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.4G"
tar_bytes = 3568099328

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "582M"
zstd_bytes = 609639320

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231023"
previous_tag = "2023-10-23"
previous_file = "swift_amd64_2023-10-23_12-27-rootfs.tar.zst"
previous_sha256 = "3501a5d0d67f07d6a5b76dcc49bd2af55edbb51a376c1c0563926bf9d673f507"

current_version = "latest02"
current_date = "20240219"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=swift_amd64
# ROOTFS_FILE=swift_amd64_2024-02-19_12-25-rootfs.tar.zst
# SHA256SUM=3fbc4107547fbec09d27caeee58a266fd4c5d0b5f6f9cab54db59139ae8c83ff
# BUILD_DATE=20240219
# BUILD_TAG=2024-02-19
# STATUS=completed
# VERSION=latest02
# END_TIME=12:25

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-19
begin = 2024-02-19 12:02:37.584923461+00:00
start-sync_0 = 12:06:24
start-zstd = 12:08:21
start-sync_1 = 12:24:54
end-sync_1 = 12:25:23
end = 2024-02-19 12:25:23.171148316+00:00

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
Swift version 5.11-dev (LLVM 48dba337c6a2104, Swift 823db1fc0821481)
Target: x86_64-unknown-linux-gnu
'''
```
