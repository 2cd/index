# test-hello-arm64

## How to run it?

```shell
docker run \
    -it \
    --name test-hello-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/test-hello-arm64
```

## How to exec shell?

```shell
    docker exec -it test-hello-arm64 sh
```

## build info

```toml
[main]
name = "test"
tag = ["hello", "2021-11-19", "test"]
os = "alpine"
release = "edge"
arch = "arm64"
nogui = true

# If the value is false, then the container will not be downloaded.
completed = true

[file]
name = "test-hello-arm64_2021-11-19_18-22.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "c0f53e392d52e4fee0c67be8290fbab31e37786692532d62b0385e8a9511c615"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "9.6M"
tar-bytes = 9996288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "5.4M"
zstd-bytes = 5598993

[compatibility]
compatible_mode = true
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=test-hello-arm64_2021-11-19_18-22.tar.zst
# BUILD_DATE=20211119
# STATUS=completed
# VERSION=latest02
# END_TIME=18:22

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-19 18:21:49.793404936+00:00
start-sync_0 = 18:22:00
start-zstd = 18:22:04
start-sync_1 = 18:22:05
end-sync_1 = 18:22:10
end = 2021-11-19 18:22:10.462322316+00:00

[server]
name = docker
node = 4
repo = "cake233/test-hello-arm64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
