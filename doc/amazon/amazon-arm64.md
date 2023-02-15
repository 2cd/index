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
tag = ["base", "2023-02-15"]
os = "amazon"
release = "base"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "amazon_arm64_2023-02-15_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "de2552389918d6b315917c95fe789070028dacbf01afa51a703d7ebb5c1e795a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "335M"
tar_bytes = 350850560

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "52M"
zstd_bytes = 53933678

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230115"
previous_tag = "2023-01-15"
previous_file = "amazon_arm64_2023-01-15_00-06-rootfs.tar.zst"
previous_sha256 = "794619bdd26a46cfa20616f2c208afd317406e60349860edefc97fa2f0358e2f"

current_version = "latest01"
current_date = "20230215"
old_file = "amazon_arm64_2022-12-15_00-06-rootfs.tar.zst"
old_sha256 = "48b2ead371ba289dce04dc1dbcaac949affa917156b89ea5483d32020a8a79eb"
# edition 2021
# DISTRO_NAME=amazon_arm64
# ROOTFS_FILE=amazon_arm64_2023-02-15_00-05-rootfs.tar.zst
# SHA256SUM=de2552389918d6b315917c95fe789070028dacbf01afa51a703d7ebb5c1e795a
# BUILD_DATE=20230215
# BUILD_TAG=2023-02-15
# STATUS=completed
# VERSION=latest01
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-15
begin = 2023-02-15 00:03:17.389585542+00:00
start-sync_0 = 00:04:35
start-zstd = 00:04:54
start-sync_1 = 00:05:41
end-sync_1 = 00:05:49
end = 2023-02-15 00:05:49.327953671+00:00

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
