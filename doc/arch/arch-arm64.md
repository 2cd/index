# arch-arm64

## How to run it?

```shell
docker run \
    -it \
    --name arch-arm64 \
    cake233/arch-arm64
```

## How to exec shell?

```shell
    docker exec -it arch-arm64 sh
```

## arch-arm64.toml

```toml
[main]
name = "arch"
tag = ["base", "2021-12-12"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "arch_arm64_2021-12-12_05-42.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "f22f33aeb015c6e8366a3a8720c08abcea3ca2e552dddb90746de6d1097055fc"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "641M"
tar_bytes = 671778304

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "177M"
zstd_bytes = 184926624

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20211212"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch_arm64_2021-12-12_05-42-rootfs.tar.zst
# SHA256SUM=f22f33aeb015c6e8366a3a8720c08abcea3ca2e552dddb90746de6d1097055fc
# BUILD_DATE=20211212
# BUILD_TAG=2021-12-12
# STATUS=completed
# VERSION=latest01
# END_TIME=05:42

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-12
begin = 2021-12-12 05:39:30.511849360+00:00
start-sync_0 = 05:41:03
start-zstd = 05:41:51
start-sync_1 = 05:42:03
end-sync_1 = 05:42:21
end = 2021-12-12 05:42:21.092094718+00:00

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
current = false
previous = false
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
