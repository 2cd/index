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
tag = ["base", "2022-04-22"]
os = "amazon"
release = "base"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "amazon_arm64_2022-04-22_05-55.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "252f5db23e55d2aaae401eda8f292756d4356c300506140e262e64137e1f8992"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "335M"
tar_bytes = 350253056

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "52M"
zstd_bytes = 53849455

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220422"
previous_tag = "2022-04-22"
previous_file = "amazon_arm64_2022-04-22_04-13-rootfs.tar.zst"
previous_sha256 = "ecc5e6a57f31710eda8b0d63e7c1313aa4cc393f0a1eba840842ddb204a077a8"

current_version = "latest02"
current_date = "20220422"
old_file = "amazon_arm64_2022-04-22_05-19-rootfs.tar.zst"
old_sha256 = "8bf9e2f2d5fe4064fb9f18af6ea5006e9b2bbd26fac7eace4d9768fbca7c990f"
# edition 2021
# DISTRO_NAME=amazon_arm64
# ROOTFS_FILE=amazon_arm64_2022-04-22_05-55-rootfs.tar.zst
# SHA256SUM=252f5db23e55d2aaae401eda8f292756d4356c300506140e262e64137e1f8992
# BUILD_DATE=20220422
# BUILD_TAG=2022-04-22
# STATUS=completed
# VERSION=latest02
# END_TIME=05:55

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-22
begin = 2022-04-22 05:51:53.383417438+00:00
start-sync_0 = 05:53:47
start-zstd = 05:54:18
start-sync_1 = 05:55:16
end-sync_1 = 05:55:29
end = 2022-04-22 05:55:29.157428946+00:00

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
current = false
previous = false
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
previous = false
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
