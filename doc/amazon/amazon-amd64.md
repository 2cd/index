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
tag = ["base", "2022-04-26"]
os = "amazon"
release = "base"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "amazon_amd64_2022-04-26_02-40.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1aac7a9ca61ebe78d945cb562cd7b7bf59e6eb1831ffe309f2714335fcd2eac4"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "300M"
tar_bytes = 314541056

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "51M"
zstd_bytes = 53360726

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220422"
previous_tag = "2022-04-22"
previous_file = "amazon_amd64_2022-04-22_04-13-rootfs.tar.zst"
previous_sha256 = "4a211daa6909c7c88f20bf2a12a01bd75207fee8b603be2a2c5eb7063449fed6"

current_version = "latest02"
current_date = "20220426"
old_file = "amazon_amd64_2022-04-22_09-49-rootfs.tar.zst"
old_sha256 = "44cc937b6d01ac1bc83ace5f399ba6f64e8620abced1177dd7bc379071141b2e"
# edition 2021
# DISTRO_NAME=amazon_amd64
# ROOTFS_FILE=amazon_amd64_2022-04-26_02-40-rootfs.tar.zst
# SHA256SUM=1aac7a9ca61ebe78d945cb562cd7b7bf59e6eb1831ffe309f2714335fcd2eac4
# BUILD_DATE=20220426
# BUILD_TAG=2022-04-26
# STATUS=completed
# VERSION=latest02
# END_TIME=02:40

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-26
begin = 2022-04-26 02:37:56.552249736+00:00
start-sync_0 = 02:38:34
start-zstd = 02:38:59
start-sync_1 = 02:39:55
end-sync_1 = 02:40:06
end = 2022-04-26 02:40:06.044254007+00:00

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
