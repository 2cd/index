# euler-arm64

## How to run it?

```sh
docker run \
    -it \
    --name euler-arm64 \
    cake233/euler-arm64
```

## How to exec shell?

```sh
docker exec -it euler-arm64 sh
```

## euler-arm64.toml

```toml
[main]
name = "euler"
tag = ["base", "2022-06-15"]
os = "euler"
release = "base"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "euler_arm64_2022-06-15_00-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "14302fc2a38cdc34b215d86ae9b698456ac1d631dfb1704118ffeb193a11fec1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "481M"
tar_bytes = 503731200

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "68M"
zstd_bytes = 70943728

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220515"
previous_tag = "2022-05-15"
previous_file = "euler_arm64_2022-05-15_00-09-rootfs.tar.zst"
previous_sha256 = "ed155045281e49e522c1e3d0a32f65f86f6ddf4d191ab5892fa3f29978c5e126"

current_version = "latest01"
current_date = "20220615"
old_file = "euler_arm64_2022-04-22_00-51-rootfs.tar.zst"
old_sha256 = "3b229d82a7c24481bb77a99aa6c0a5118047233698ad3144e8da652a348a572f"
# edition 2021
# DISTRO_NAME=euler_arm64
# ROOTFS_FILE=euler_arm64_2022-06-15_00-10-rootfs.tar.zst
# SHA256SUM=14302fc2a38cdc34b215d86ae9b698456ac1d631dfb1704118ffeb193a11fec1
# BUILD_DATE=20220615
# BUILD_TAG=2022-06-15
# STATUS=completed
# VERSION=latest01
# END_TIME=00:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-15
begin = 2022-06-15 00:04:16.980109656+00:00
start-sync_0 = 00:08:17
start-zstd = 00:08:41
start-sync_1 = 00:09:59
end-sync_1 = 00:10:11
end = 2022-06-15 00:10:11.669786762+00:00

[server]
repo = "cake233/euler-arm64"

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
