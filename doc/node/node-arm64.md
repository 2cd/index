# node-arm64

## How to run it?

```sh
docker run \
    -it \
    --name node-arm64 \
    cake233/node-arm64
```

## How to exec shell?

```sh
docker exec -it node-arm64 bash
```

## node-arm64.toml

```toml
[main]
name = "node"
tag = ["latest", "2021-12-20"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "node_arm64_2021-12-20_12-07.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "e8cac377a614d3822dfc8dfa849d577b274b44c425a66c9178570e19a60a0ec4"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "948M"
tar_bytes = 993265152

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "228M"
zstd_bytes = 238749366

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211206"
previous_tag = "2021-12-06"
previous_file = "node_arm64_2021-12-06_20-11-rootfs.tar.zst"
previous_sha256 = ""

current_version = "latest02"
current_date = "20211220"
old_file = "node_arm64_2021-11-28_23-07-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node_arm64_2021-12-20_12-07-rootfs.tar.zst
# SHA256SUM=e8cac377a614d3822dfc8dfa849d577b274b44c425a66c9178570e19a60a0ec4
# BUILD_DATE=20211220
# BUILD_TAG=2021-12-20
# STATUS=completed
# VERSION=latest02
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-20
begin = 2021-12-20 12:02:29.460702100+00:00
start-sync_0 = 12:05:00
start-zstd = 12:05:18
start-sync_1 = 12:07:35
end-sync_1 = 12:07:56
end = 2021-12-20 12:07:56.328353066+00:00

[server]
repo = "cake233/node-arm64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u2) 2.31'
node = 'v17.2.0'
yarn = '1.22.15'
npm = '8.1.4'
```
