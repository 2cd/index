# node-amd64

## How to run it?

```sh
docker run \
    -it \
    --name node-amd64 \
    cake233/node-amd64
```

## How to exec shell?

```sh
docker exec -it node-amd64 bash
```

## node-amd64.toml

```toml
[main]
name = "node"
tag = ["latest", "2023-06-05"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_amd64_2023-06-05_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "76eda00055e4182b6a8a6386813ba5962a6fc7f9dd0a7281b55aa18769967d44"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1003M"
tar_bytes = 1050852864

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "201M"
zstd_bytes = 209901985

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230522"
previous_tag = "2023-05-22"
previous_file = "node_amd64_2023-05-22_12-14-rootfs.tar.zst"
previous_sha256 = "db9b4b5c0e99371c582995ee00c10ea407fd684a83887f0de057a09ca9dff946"

current_version = "latest01"
current_date = "20230605"
old_file = "node_amd64_2023-05-08_12-14-rootfs.tar.zst"
old_sha256 = "6a79173944b3b5ef15240e3bb67a9367d5f53a679aa90459cb02c6a80465a463"
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node_amd64_2023-06-05_12-12-rootfs.tar.zst
# SHA256SUM=76eda00055e4182b6a8a6386813ba5962a6fc7f9dd0a7281b55aa18769967d44
# BUILD_DATE=20230605
# BUILD_TAG=2023-06-05
# STATUS=completed
# VERSION=latest01
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-05
begin = 2023-06-05 12:02:37.607176817+00:00
start-sync_0 = 12:03:48
start-zstd = 12:04:03
start-sync_1 = 12:12:17
end-sync_1 = 12:12:33
end = 2023-06-05 12:12:33.301029317+00:00

[server]
repo = "cake233/node-amd64"

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u6) 2.31'
node = 'v20.2.0'
yarn = '1.22.19'
npm = '9.6.6'
```
