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
name = "arch-arm64_2021-11-27_13-15.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "1dc1c7c6e5bbd6dd79f549eff35ca15a8d58dee9dcd9fba29f633961ce9c121c"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "641M"
tar-bytes = 671664640

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "177M"
zstd-bytes = 184605302

[compatibility]
compatible_mode = true
rootfs_version = "latest02"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-arm64_2021-11-27_13-15.tar.zst
# BUILD_DATE=20211127
# STATUS=completed
# VERSION=latest02
# END_TIME=13:15

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-27 13:12:06.192497780+00:00
start-sync_0 = 13:13:33
start-zstd = 13:14:17
start-sync_1 = 13:14:50
end-sync_1 = 13:15:09
end = 2021-11-27 13:15:09.227661309+00:00

[server]
name = "docker"
node = 4
repo = "cake233/arch-arm64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
