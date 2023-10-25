# arch-arm64

## How to run it?

```sh
docker run \
    -it \
    --name arch-arm64 \
    cake233/arch-arm64
```

## How to exec shell?

```sh
docker exec -it arch-arm64 sh
```

## arch-arm64.toml

```toml
[main]
name = "arch"
tag = ["base", "2023-10-25"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch_arm64_2023-10-25_00-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "39e5d3f8a2ca03903f02e1f66d57f7cba151c60f9fd4a51ffebe4756e31d6c48"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "913M"
tar_bytes = 957125632

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "257M"
zstd_bytes = 268973498

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20231025"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch_arm64_2023-10-25_00-09-rootfs.tar.zst
# SHA256SUM=39e5d3f8a2ca03903f02e1f66d57f7cba151c60f9fd4a51ffebe4756e31d6c48
# BUILD_DATE=20231025
# BUILD_TAG=2023-10-25
# STATUS=completed
# VERSION=latest01
# END_TIME=00:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-25
begin = 2023-10-25 00:02:30.210749445+00:00
start-sync_0 = 00:07:29
start-zstd = 00:08:14
start-sync_1 = 00:08:41
end-sync_1 = 00:09:10
end = 2023-10-25 00:09:10.491108090+00:00

[server]
repo = "cake233/arch-arm64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = true
previous = false
in_sync = false
split = false

[server.node3]
name = "azure"
current = true
previous = false
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
