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
tag = ["base", "2021-11-27"]
os = "arch"
release = "latest"
arch = "arm64"
nogui = true

# If the value is false, then the container will not be downloaded.
completed = true

[file]
name = "arch-arm64_2021-11-27_10-56.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "c6c24d4afbf55ada054a62d6967a9010d30a17447428e7aacd140783d15c222b"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "626M"
tar-bytes = 656106496

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "166M"
zstd-bytes = 173176973

[compatibility]
compatible_mode = true
rootfs_version = "latest02"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-arm64_2021-11-27_10-56.tar.zst
# BUILD_DATE=20211127
# STATUS=completed
# VERSION=latest02
# END_TIME=10:56

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-27 10:52:36.423415422+00:00
start-sync_0 = 10:54:20
start-zstd = 10:55:15
start-sync_1 = 10:55:54
end-sync_1 = 10:56:14
end = 2021-11-27 10:56:14.732468726+00:00

[server]
name = "docker"
node = 4
repo = "cake233/arch-arm64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
