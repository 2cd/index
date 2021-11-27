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
name = "arch-amd64_2021-11-27_13-15.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "6f1e6037672292d136802ebbd068170a9829afe71517bb7ca2594343f4461cab"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "622M"
tar-bytes = 651251200

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "178M"
zstd-bytes = 186261051

[compatibility]
compatible_mode = true
rootfs_version = "latest02"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-amd64_2021-11-27_13-15.tar.zst
# BUILD_DATE=20211127
# STATUS=completed
# VERSION=latest02
# END_TIME=13:15

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-27 13:12:05.674489339+00:00
start-sync_0 = 13:13:19
start-zstd = 13:14:08
start-sync_1 = 13:14:43
end-sync_1 = 13:15:01
end = 2021-11-27 13:15:01.873082965+00:00

[server]
name = "docker"
node = 4
repo = "cake233/arch-amd64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
