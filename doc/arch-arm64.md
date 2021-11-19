# arch-arm64

## How to run it?

```shell
docker run \
    -it \
    --name arch-arm64 \
    cake233/arch-arm64
```

## How to exec shell?

```shell
    docker exec -it arch-arm64 sh
```

## build info

```toml
[main]
name = "arch"
tag = ["base", "2021-11-19"]
os = "arch"
release = "latest"
arch = "arm64"
nogui = true

# If the value is false, then the container will not be downloaded.
completed = true

[file]
name = "arch-arm64_2021-11-19_23-12.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "2539096bb48ae7c03fb01d5ed896298115c20d846c4577a79c48347f7c589960"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "626M"
tar-bytes = 655432704

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "165M"
zstd-bytes = 172900764

[compatibility]
compatible_mode = true
rootfs_version = "latest02"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-arm64_2021-11-19_23-12.tar.zst
# BUILD_DATE=20211119
# STATUS=completed
# VERSION=latest02
# END_TIME=23:12

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-19 23:09:40.352060425+00:00
start-sync_0 = 23:11:07
start-zstd = 23:11:50
start-sync_1 = 23:12:20
end-sync_1 = 23:12:36
end = 2021-11-19 23:12:36.590862889+00:00

[server]
name = "docker"
node = 4
repo = "cake233/arch-arm64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
