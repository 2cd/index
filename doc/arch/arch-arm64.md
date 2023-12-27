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
tag = ["base", "2023-12-27"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch_arm64_2023-12-27_00-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b2dc5ca18114cbf5d8c861e88037d52e29668eac4222662b3e2c32e5a40b704e"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "920M"
tar_bytes = 964073472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "260M"
zstd_bytes = 271962137

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20231227"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch_arm64_2023-12-27_00-07-rootfs.tar.zst
# SHA256SUM=b2dc5ca18114cbf5d8c861e88037d52e29668eac4222662b3e2c32e5a40b704e
# BUILD_DATE=20231227
# BUILD_TAG=2023-12-27
# STATUS=completed
# VERSION=latest01
# END_TIME=00:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-27
begin = 2023-12-27 00:02:29.088910763+00:00
start-sync_0 = 00:06:48
start-zstd = 00:07:27
start-sync_1 = 00:07:43
end-sync_1 = 00:07:59
end = 2023-12-27 00:07:59.908482328+00:00

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
