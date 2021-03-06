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
tag = ["base", "2022-06-15"]
os = "cblmariner"
release = "base"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "cblmariner_arm64_2022-06-15_00-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2b2cd9c978454a576dad6ca3299167b923485894f7b26ecc70ade12158933ccf"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "237M"
tar_bytes = 248117760

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "66M"
zstd_bytes = 69153387

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220515"
previous_tag = "2022-05-15"
previous_file = "cblmariner_arm64_2022-05-15_00-06-rootfs.tar.zst"
previous_sha256 = "d8876f2f6121906875212c6a7e01bd067c6fd39b1e16474ee01444ab5eed9703"

current_version = "latest01"
current_date = "20220615"
old_file = "cblmariner_arm64_2022-04-22_08-54-rootfs.tar.zst"
old_sha256 = "b66c8208bdd58ac1b1fb1f46927df20761181ba0c0bad0e04141d6fc5c7ff3e8"
# edition 2021
# DISTRO_NAME=cblmariner_arm64
# ROOTFS_FILE=cblmariner_arm64_2022-06-15_00-08-rootfs.tar.zst
# SHA256SUM=2b2cd9c978454a576dad6ca3299167b923485894f7b26ecc70ade12158933ccf
# BUILD_DATE=20220615
# BUILD_TAG=2022-06-15
# STATUS=completed
# VERSION=latest01
# END_TIME=00:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-15
begin = 2022-06-15 00:04:17.143985596+00:00
start-sync_0 = 00:06:44
start-zstd = 00:07:01
start-sync_1 = 00:08:09
end-sync_1 = 00:08:19
end = 2022-06-15 00:08:19.845823804+00:00

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
