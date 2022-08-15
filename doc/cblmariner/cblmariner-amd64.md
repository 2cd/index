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
tag = ["base", "2022-08-15"]
os = "cblmariner"
release = "base"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "cblmariner_amd64_2022-08-15_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4d2b94d7e193ac0b07873b291d8b652d65d852bcb45e7391801ca95388a5202c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "248M"
tar_bytes = 259594752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "71M"
zstd_bytes = 74214909

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220615"
previous_tag = "2022-06-15"
previous_file = "cblmariner_amd64_2022-06-15_00-05-rootfs.tar.zst"
previous_sha256 = "1f797b1e524a55e8f376c29623e07e9deda3681fc479f6123201bc1ca7c3d418"

current_version = "latest02"
current_date = "20220815"
old_file = "cblmariner_amd64_2022-05-15_00-05-rootfs.tar.zst"
old_sha256 = "f8c030f55fde075748f71ee9caa8dfddcd2930c8e27cb7763307fc5454c5369b"
# edition 2021
# DISTRO_NAME=cblmariner_amd64
# ROOTFS_FILE=cblmariner_amd64_2022-08-15_00-05-rootfs.tar.zst
# SHA256SUM=4d2b94d7e193ac0b07873b291d8b652d65d852bcb45e7391801ca95388a5202c
# BUILD_DATE=20220815
# BUILD_TAG=2022-08-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-15
begin = 2022-08-15 00:03:25.692605099+00:00
start-sync_0 = 00:04:14
start-zstd = 00:04:36
start-sync_1 = 00:05:40
end-sync_1 = 00:05:53
end = 2022-08-15 00:05:53.867152354+00:00

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
