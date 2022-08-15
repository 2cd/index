# amazon-amd64

## How to run it?

```sh
docker run \
    -it \
    --name amazon-amd64 \
    cake233/amazon-amd64
```

## How to exec shell?

```sh
docker exec -it amazon-amd64 sh
```

## amazon-amd64.toml

```toml
[main]
name = "amazon"
tag = ["base", "2022-08-15"]
os = "amazon"
release = "base"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "amazon_amd64_2022-08-15_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "da8743d3d5087c2ea0b9b7120670683e146328ee5b5bb779d01c1c8db2e73541"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "301M"
tar_bytes = 315212288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "51M"
zstd_bytes = 53404359

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220715"
previous_tag = "2022-07-15"
previous_file = "amazon_amd64_2022-07-15_00-05-rootfs.tar.zst"
previous_sha256 = "a91a1ba6575a57b3b87c19f75e372ca6dbe462c135d7da670b9461c7e15298c2"

current_version = "latest02"
current_date = "20220815"
old_file = "amazon_amd64_2022-06-15_00-05-rootfs.tar.zst"
old_sha256 = "618a1115102353a53ee6be008eb2767dc1b12145cf1b1e003367bd3ca999de74"
# edition 2021
# DISTRO_NAME=amazon_amd64
# ROOTFS_FILE=amazon_amd64_2022-08-15_00-05-rootfs.tar.zst
# SHA256SUM=da8743d3d5087c2ea0b9b7120670683e146328ee5b5bb779d01c1c8db2e73541
# BUILD_DATE=20220815
# BUILD_TAG=2022-08-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-15
begin = 2022-08-15 00:03:21.536994747+00:00
start-sync_0 = 00:04:13
start-zstd = 00:04:40
start-sync_1 = 00:05:30
end-sync_1 = 00:05:42
end = 2022-08-15 00:05:42.909780613+00:00

[server]
repo = "cake233/amazon-amd64"

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
