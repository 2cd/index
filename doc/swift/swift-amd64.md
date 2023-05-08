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
tag = ["latest", "2023-05-08", "nightly"]
os = "ubuntu"
release = "focal"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_amd64_2023-05-08_12-27.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c1a651f22815d44ecd1becd3ff688d57b1b65310f9ef07fa4f5cbff2ce8efb9d"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.7G"
tar_bytes = 2884601856

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "498M"
zstd_bytes = 521566465

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230424"
previous_tag = "2023-04-24"
previous_file = "swift_amd64_2023-04-24_12-26-rootfs.tar.zst"
previous_sha256 = "491bea3e228c97dc3da85acd09d302df271efe9cd88778b84ff0b4d607ac84b4"

current_version = "latest02"
current_date = "20230508"
old_file = "swift_amd64_2023-04-10_12-27-rootfs.tar.zst"
old_sha256 = "719ce01cb7c372eae8ecf8ded1a6cf68b1e2b418964ed70735068075b0a1cf16"
# edition 2021
# DISTRO_NAME=swift_amd64
# ROOTFS_FILE=swift_amd64_2023-05-08_12-27-rootfs.tar.zst
# SHA256SUM=c1a651f22815d44ecd1becd3ff688d57b1b65310f9ef07fa4f5cbff2ce8efb9d
# BUILD_DATE=20230508
# BUILD_TAG=2023-05-08
# STATUS=completed
# VERSION=latest02
# END_TIME=12:27

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-08
begin = 2023-05-08 12:02:47.896295242+00:00
start-sync_0 = 12:06:14
start-zstd = 12:08:13
start-sync_1 = 12:27:13
end-sync_1 = 12:27:47
end = 2023-05-08 12:27:47.588992015+00:00

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
Swift version 5.9-dev (LLVM a2ca92a9bd78abf, Swift a1dc63ec467a108)
Target: x86_64-unknown-linux-gnu
'''
```
