# node-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name node-alpine-arm64 \
    cake233/node-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it node-alpine-arm64 bash
```

## node-alpine-arm64.toml

```toml
[main]
name = "node"
tag = ["alpine", "2023-02-27", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_arm64_2023-02-27_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d41daf1ec258d6104631e9f95f92d40694b2b5a07a5ae6f820c12428bebfe66b"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "194M"
tar_bytes = 202670080

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "34M"
zstd_bytes = 35182213

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230213"
previous_tag = "2023-02-13"
previous_file = "node-musl_arm64_2023-02-13_12-05-rootfs.tar.zst"
previous_sha256 = "15143f739737d06a48ab47fea25b8d98ed33dcb385f0bce1763a976b5a3b48b8"

current_version = "latest02"
current_date = "20230227"
old_file = "node-musl_arm64_2023-01-30_12-05-rootfs.tar.zst"
old_sha256 = "9c493f029e6d39b4e60fa74e06c923b6f21133554d1bd58013552d4dd0fdc199"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node-musl_arm64_2023-02-27_12-05-rootfs.tar.zst
# SHA256SUM=d41daf1ec258d6104631e9f95f92d40694b2b5a07a5ae6f820c12428bebfe66b
# BUILD_DATE=20230227
# BUILD_TAG=2023-02-27
# STATUS=completed
# VERSION=latest02
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-27
begin = 2023-02-27 12:02:41.374918116+00:00
start-sync_0 = 12:03:48
start-zstd = 12:04:01
start-sync_1 = 12:05:10
end-sync_1 = 12:05:20
end = 2023-02-27 12:05:20.854807377+00:00

[server]
repo = "cake233/node-alpine-arm64"

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (aarch64) Version 1.2.3'
node = 'v19.7.0'
yarn = '1.22.19'
npm = '9.5.0'
```
