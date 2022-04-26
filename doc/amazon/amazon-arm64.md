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
tag = ["base", "2022-04-26"]
os = "amazon"
release = "base"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "amazon_arm64_2022-04-26_02-41.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6f56ffff24924ffcb55ec4ab30dea60ac770cc8d24691400aae32c86a552cb9e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "335M"
tar_bytes = 350364160

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "52M"
zstd_bytes = 53884113

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220422"
previous_tag = "2022-04-22"
previous_file = "amazon_arm64_2022-04-22_04-13-rootfs.tar.zst"
previous_sha256 = "ecc5e6a57f31710eda8b0d63e7c1313aa4cc393f0a1eba840842ddb204a077a8"

current_version = "latest02"
current_date = "20220426"
old_file = "amazon_arm64_2022-04-22_09-50-rootfs.tar.zst"
old_sha256 = "fe7ea992034e767e5018690cd4975f6008e01697d1df91c94fd1b65185540168"
# edition 2021
# DISTRO_NAME=amazon_arm64
# ROOTFS_FILE=amazon_arm64_2022-04-26_02-41-rootfs.tar.zst
# SHA256SUM=6f56ffff24924ffcb55ec4ab30dea60ac770cc8d24691400aae32c86a552cb9e
# BUILD_DATE=20220426
# BUILD_TAG=2022-04-26
# STATUS=completed
# VERSION=latest02
# END_TIME=02:41

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-26
begin = 2022-04-26 02:37:54.903645193+00:00
start-sync_0 = 02:39:36
start-zstd = 02:40:02
start-sync_1 = 02:40:56
end-sync_1 = 02:41:09
end = 2022-04-26 02:41:09.390517858+00:00

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
