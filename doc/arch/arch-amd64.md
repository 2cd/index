# arch-amd64

## How to run it?

```sh
docker run \
    -it \
    --name arch-amd64 \
    cake233/arch-amd64
```

## How to exec shell?

```sh
docker exec -it arch-amd64 sh
```

## arch-amd64.toml

```toml
[main]
name = "arch"
tag = ["base", "2023-04-25"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch_amd64_2023-04-25_21-44.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f8c222a442e63989e5e6fd5e29477329236afeeb9f53a6eaec3d406ae3f2f280"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "949M"
tar_bytes = 994162688

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "270M"
zstd_bytes = 282816949

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230425"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch_amd64_2023-04-25_21-44-rootfs.tar.zst
# SHA256SUM=f8c222a442e63989e5e6fd5e29477329236afeeb9f53a6eaec3d406ae3f2f280
# BUILD_DATE=20230425
# BUILD_TAG=2023-04-25
# STATUS=completed
# VERSION=latest01
# END_TIME=21:44

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-25
begin = 2023-04-25 21:41:54.950858638+00:00
start-sync_0 = 21:43:14
start-zstd = 21:43:57
start-sync_1 = 21:44:21
end-sync_1 = 21:44:42
end = 2023-04-25 21:44:42.517358992+00:00

[server]
repo = "cake233/arch-amd64"

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
