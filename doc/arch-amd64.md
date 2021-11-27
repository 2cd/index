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
tag = ["base", "2021-11-27"]
os = "arch"
release = "latest"
arch = "amd64"
nogui = true

# If the value is false, then the container will not be downloaded.
completed = true

[file]
name = "arch-amd64_2021-11-27_10-55.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "271fdf2b1ef7aa1d20cd295fb8209e213201f009f89f678a42fd135a3b84a440"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "607M"
tar-bytes = 636300288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "168M"
zstd-bytes = 175407132

[compatibility]
compatible_mode = true
rootfs_version = "latest02"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-amd64_2021-11-27_10-55.tar.zst
# BUILD_DATE=20211127
# STATUS=completed
# VERSION=latest02
# END_TIME=10:55

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-27 10:52:32.713096194+00:00
start-sync_0 = 10:53:47
start-zstd = 10:54:35
start-sync_1 = 10:55:08
end-sync_1 = 10:55:25
end = 2021-11-27 10:55:25.151995975+00:00

[server]
name = "docker"
node = 4
repo = "cake233/arch-amd64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
