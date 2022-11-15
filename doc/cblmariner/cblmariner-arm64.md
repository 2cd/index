# cblmariner-arm64

## How to run it?

```sh
docker run \
    -it \
    --name cblmariner-arm64 \
    cake233/cblmariner-arm64
```

## How to exec shell?

```sh
docker exec -it cblmariner-arm64 sh
```

## cblmariner-arm64.toml

```toml
[main]
name = "cblmariner"
tag = ["base", "2022-11-15"]
os = "cblmariner"
release = "base"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "cblmariner_arm64_2022-11-15_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fb7162c6451c47fe2fa2ef91474b2d48e8d885b0bce9e863dd71b7a8cf76ec33"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "238M"
tar_bytes = 249496064

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "70M"
zstd_bytes = 73148549

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221015"
previous_tag = "2022-10-15"
previous_file = "cblmariner_arm64_2022-10-15_00-06-rootfs.tar.zst"
previous_sha256 = "99e822d0beb87b7d81af268ed39801e89445c8f73c3581593732168d2039d5ee"

current_version = "latest01"
current_date = "20221115"
old_file = "cblmariner_arm64_2022-09-15_00-07-rootfs.tar.zst"
old_sha256 = "b9a8833072228bcde0a862cc2b2a570b4498a60f9ff3dc061ab0f307ebddc261"
# edition 2021
# DISTRO_NAME=cblmariner_arm64
# ROOTFS_FILE=cblmariner_arm64_2022-11-15_00-06-rootfs.tar.zst
# SHA256SUM=fb7162c6451c47fe2fa2ef91474b2d48e8d885b0bce9e863dd71b7a8cf76ec33
# BUILD_DATE=20221115
# BUILD_TAG=2022-11-15
# STATUS=completed
# VERSION=latest01
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-15
begin = 2022-11-15 00:03:16.422802934+00:00
start-sync_0 = 00:05:30
start-zstd = 00:05:45
start-sync_1 = 00:06:32
end-sync_1 = 00:06:40
end = 2022-11-15 00:06:40.598993842+00:00

[server]
repo = "cake233/cblmariner-arm64"

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
```
