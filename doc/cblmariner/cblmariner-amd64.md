# cblmariner-amd64

## How to run it?

```sh
docker run \
    -it \
    --name cblmariner-amd64 \
    cake233/cblmariner-amd64
```

## How to exec shell?

```sh
docker exec -it cblmariner-amd64 sh
```

## cblmariner-amd64.toml

```toml
[main]
name = "cblmariner"
tag = ["base", "2023-03-15"]
os = "cblmariner"
release = "base"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "cblmariner_amd64_2023-03-15_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "868fa6c55bc8d6e5f36af5e0f30d3f4de22f9195a6133010642509327bdc878d"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "273M"
tar_bytes = 285507584

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "85M"
zstd_bytes = 88283092

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230215"
previous_tag = "2023-02-15"
previous_file = "cblmariner_amd64_2023-02-15_00-05-rootfs.tar.zst"
previous_sha256 = "06fb263cb3ab063c2ab87f0adc2ae5257e5acd4e4de32afda44172713af6e1ff"

current_version = "latest01"
current_date = "20230315"
old_file = "cblmariner_amd64_2023-01-15_00-05-rootfs.tar.zst"
old_sha256 = "8ea14c60b1b44842c7008d6da30ba0cca7f197adb4e25f39321da9cdef3ef66d"
# edition 2021
# DISTRO_NAME=cblmariner_amd64
# ROOTFS_FILE=cblmariner_amd64_2023-03-15_00-05-rootfs.tar.zst
# SHA256SUM=868fa6c55bc8d6e5f36af5e0f30d3f4de22f9195a6133010642509327bdc878d
# BUILD_DATE=20230315
# BUILD_TAG=2023-03-15
# STATUS=completed
# VERSION=latest01
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-15
begin = 2023-03-15 00:03:18.179494411+00:00
start-sync_0 = 00:04:07
start-zstd = 00:04:27
start-sync_1 = 00:05:26
end-sync_1 = 00:05:39
end = 2023-03-15 00:05:39.232654552+00:00

[server]
repo = "cake233/cblmariner-amd64"

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