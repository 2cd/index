# cblmariner-arm64

## How to run it?

```sh
docker run \
    -it \
    --name cblmariner-arm64 \
    cake233/cblmariner-arm64
```

## How to exec shell?

```sh
docker exec -it cblmariner-arm64 sh
```

## cblmariner-arm64.toml

```toml
[main]
name = "cblmariner"
tag = ["base", "2023-02-15"]
os = "cblmariner"
release = "base"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "cblmariner_arm64_2023-02-15_00-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5f36aadc43b6d1d64e91a94fd8d3d05a39db406d53e5d841f4eb2ecfd20d78d1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "248M"
tar_bytes = 259119104

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "75M"
zstd_bytes = 77811953

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230115"
previous_tag = "2023-01-15"
previous_file = "cblmariner_arm64_2023-01-15_00-08-rootfs.tar.zst"
previous_sha256 = "7874a28e7baac751d6a501a345271c3e5ff1282c1c01c7c5c90c5f336dd5f21f"

current_version = "latest02"
current_date = "20230215"
old_file = "cblmariner_arm64_2022-12-15_00-07-rootfs.tar.zst"
old_sha256 = "d002ba3d90919f2f018c444c3bdc5980571e1a5200c1c9eade0314e9bb5ff545"
# edition 2021
# DISTRO_NAME=cblmariner_arm64
# ROOTFS_FILE=cblmariner_arm64_2023-02-15_00-07-rootfs.tar.zst
# SHA256SUM=5f36aadc43b6d1d64e91a94fd8d3d05a39db406d53e5d841f4eb2ecfd20d78d1
# BUILD_DATE=20230215
# BUILD_TAG=2023-02-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-15
begin = 2023-02-15 00:03:18.840344091+00:00
start-sync_0 = 00:06:02
start-zstd = 00:06:21
start-sync_1 = 00:07:11
end-sync_1 = 00:07:23
end = 2023-02-15 00:07:23.265428130+00:00

[server]
repo = "cake233/cblmariner-arm64"

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
