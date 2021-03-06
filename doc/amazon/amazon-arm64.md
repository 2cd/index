# amazon-arm64

## How to run it?

```sh
docker run \
    -it \
    --name amazon-arm64 \
    cake233/amazon-arm64
```

## How to exec shell?

```sh
docker exec -it amazon-arm64 sh
```

## amazon-arm64.toml

```toml
[main]
name = "amazon"
tag = ["base", "2022-06-15"]
os = "amazon"
release = "base"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "amazon_arm64_2022-06-15_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0cc04b9e201b9f9b06881ac369ac7f0db40240a502c3b910fca922d90f3b4e51"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "335M"
tar_bytes = 350971392

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "52M"
zstd_bytes = 53863102

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220515"
previous_tag = "2022-05-15"
previous_file = "amazon_arm64_2022-05-15_00-06-rootfs.tar.zst"
previous_sha256 = "c8eceff3418e65a52483021f5a534d1c62ccb4c57be9a31fa10dd5f20f8f4ab8"

current_version = "latest02"
current_date = "20220615"
old_file = "amazon_arm64_2022-04-26_02-41-rootfs.tar.zst"
old_sha256 = "6f56ffff24924ffcb55ec4ab30dea60ac770cc8d24691400aae32c86a552cb9e"
# edition 2021
# DISTRO_NAME=amazon_arm64
# ROOTFS_FILE=amazon_arm64_2022-06-15_00-06-rootfs.tar.zst
# SHA256SUM=0cc04b9e201b9f9b06881ac369ac7f0db40240a502c3b910fca922d90f3b4e51
# BUILD_DATE=20220615
# BUILD_TAG=2022-06-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-15
begin = 2022-06-15 00:03:58.422586356+00:00
start-sync_0 = 00:05:34
start-zstd = 00:05:56
start-sync_1 = 00:06:50
end-sync_1 = 00:06:58
end = 2022-06-15 00:06:58.836864093+00:00

[server]
repo = "cake233/amazon-arm64"

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
