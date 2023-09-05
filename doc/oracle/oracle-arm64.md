# oracle-arm64

## How to run it?

```sh
docker run \
    -it \
    --name oracle-arm64 \
    cake233/oracle-arm64
```

## How to exec shell?

```sh
docker exec -it oracle-arm64 sh
```

## oracle-arm64.toml

```toml
[main]
name = "oracle"
tag = ["base", "2023-03-15"]
os = "oracle"
release = "base"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "oracle_arm64_2023-03-15_00-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e3f37d1010c7494ba83749acc0c1422a7005042402da5e17c5e18a8a2671aa9b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "477M"
tar_bytes = 500034048

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "75M"
zstd_bytes = 78264862

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230215"
previous_tag = "2023-02-15"
previous_file = "oracle_arm64_2023-02-15_00-09-rootfs.tar.zst"
previous_sha256 = "903d7a7e459c3402c8635da058283b517cf058ac151c87785cdc836acad0fc48"

current_version = "latest02"
current_date = "20230315"
old_file = "oracle_arm64_2023-01-15_00-10-rootfs.tar.zst"
old_sha256 = "f3d6da8e946809b8a9e3823f1371363b0133d4e7993bc383411f95d3387d3c7e"
# edition 2021
# DISTRO_NAME=oracle_arm64
# ROOTFS_FILE=oracle_arm64_2023-03-15_00-09-rootfs.tar.zst
# SHA256SUM=e3f37d1010c7494ba83749acc0c1422a7005042402da5e17c5e18a8a2671aa9b
# BUILD_DATE=20230315
# BUILD_TAG=2023-03-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-15
begin = 2023-03-15 00:03:16.866195066+00:00
start-sync_0 = 00:07:55
start-zstd = 00:08:16
start-sync_1 = 00:09:37
end-sync_1 = 00:09:47
end = 2023-03-15 00:09:47.135914856+00:00

[server]
repo = "cake233/oracle-arm64"

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