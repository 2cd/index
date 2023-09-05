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
tag = ["base", "2023-03-15"]
os = "amazon"
release = "base"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "amazon_amd64_2023-03-15_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a7f260834b77fed53b1bd83a22950c34a05c197c27523b82e02acc41f56e4bf8"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "301M"
tar_bytes = 315368960

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "51M"
zstd_bytes = 53457350

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230215"
previous_tag = "2023-02-15"
previous_file = "amazon_amd64_2023-02-15_00-05-rootfs.tar.zst"
previous_sha256 = "7924dc66f700a4b38a5a604788198fbfce5bdc5fd653d6c068ebbf2e37ead6ad"

current_version = "latest01"
current_date = "20230315"
old_file = "amazon_amd64_2023-01-15_00-06-rootfs.tar.zst"
old_sha256 = "ee6ce897e2bd29d712273e7be8a59a0bc86adfd742e2cf24319db29e90321ff4"
# edition 2021
# DISTRO_NAME=amazon_amd64
# ROOTFS_FILE=amazon_amd64_2023-03-15_00-05-rootfs.tar.zst
# SHA256SUM=a7f260834b77fed53b1bd83a22950c34a05c197c27523b82e02acc41f56e4bf8
# BUILD_DATE=20230315
# BUILD_TAG=2023-03-15
# STATUS=completed
# VERSION=latest01
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-15
begin = 2023-03-15 00:03:16.594201702+00:00
start-sync_0 = 00:03:54
start-zstd = 00:04:14
start-sync_1 = 00:05:06
end-sync_1 = 00:05:14
end = 2023-03-15 00:05:14.179499484+00:00

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