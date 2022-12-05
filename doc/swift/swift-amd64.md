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
tag = ["latest", "2022-12-05", "nightly"]
os = "ubuntu"
release = "focal"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "swift_amd64_2022-12-05_12-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "97a169f93ca7397c700b868c850fe1f6f274083d77e35c365910a00eb0743f2e"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.6G"
tar_bytes = 2735336960

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "472M"
zstd_bytes = 494761039

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221121"
previous_tag = "2022-11-21"
previous_file = "swift_amd64_2022-11-21_12-24-rootfs.tar.zst"
previous_sha256 = "863681836ed8b3bdd094923349fc7c855a71dbb58ad7d395b955a243b52747cb"

current_version = "latest02"
current_date = "20221205"
old_file = "swift_amd64_2022-11-07_12-24-rootfs.tar.zst"
old_sha256 = "f3e40ccd1277d3d9060ecdcddba0fa08f66037c946dd538b3eb529840d224e46"
# edition 2021
# DISTRO_NAME=swift_amd64
# ROOTFS_FILE=swift_amd64_2022-12-05_12-28-rootfs.tar.zst
# SHA256SUM=97a169f93ca7397c700b868c850fe1f6f274083d77e35c365910a00eb0743f2e
# BUILD_DATE=20221205
# BUILD_TAG=2022-12-05
# STATUS=completed
# VERSION=latest02
# END_TIME=12:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-05
begin = 2022-12-05 12:02:30.633210533+00:00
start-sync_0 = 12:05:34
start-zstd = 12:07:39
start-sync_1 = 12:27:58
end-sync_1 = 12:28:36
end = 2022-12-05 12:28:36.873128182+00:00

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
Swift version 5.8-dev (LLVM f21cfd5346ab53b, Swift d3e96590d9319d4)
Target: x86_64-unknown-linux-gnu
'''
```
