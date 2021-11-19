# arch-amd64

## How to run it?

```shell
docker run \
    -it \
    --name arch-amd64 \
    cake233/arch-amd64
```

## How to exec shell?

```shell
    docker exec -it arch-amd64 sh
```

## build info

```toml
[main]
name = "arch"
tag = ["base", "2021-11-19"]
os = "arch"
release = "latest"
arch = "amd64"
nogui = true

# If the value is false, then the container will not be downloaded.
completed = true

[file]
name = "arch-amd64_2021-11-19_22-41.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "36a867b9d2e4158eca8a37c7170f9e50a85e5f704f36f864b3894522d1ddc20e"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "607M"
tar-bytes = 635674624

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "168M"
zstd-bytes = 175139840

[compatibility]
compatible_mode = true
rootfs_version = "latest02"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-amd64_2021-11-19_22-41.tar.zst
# BUILD_DATE=20211119
# STATUS=completed
# VERSION=latest02
# END_TIME=22:41

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-19 22:39:06.150896204+00:00
start-sync_0 = 22:40:05
start-zstd = 22:40:51
start-sync_1 = 22:41:29
end-sync_1 = 22:41:45
end = 2021-11-19 22:41:45.216116337+00:00

[server]
name = "docker"
node = 4
repo = "cake233/arch-amd64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
