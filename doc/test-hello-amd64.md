# test-hello-amd64

## How to run it?

```shell
docker run \
    -it \
    --name test-hello-amd64 \
    cake233/test-hello-amd64
```

## How to exec shell?

```shell
    docker exec -it test-hello-amd64 sh
```

## build info

```toml
[main]
name = "test"
tag = ["hello", "2021-11-19", "test"]
os = "alpine"
release = "edge"
arch = "amd64"
nogui = true

# If the value is false, then the container will not be downloaded.
completed = true

[file]
name = "test-hello-amd64_2021-11-19_18-34.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "d18a055696b8615529f97d1e604fdc03caeaf3224c04ba2d1a5ddf43e43d5ac0"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "9.9M"
tar-bytes = 10361344

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "5.5M"
zstd-bytes = 5698094

[compatibility]
compatible_mode = true
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=test-hello-amd64_2021-11-19_18-34.tar.zst
# BUILD_DATE=20211119
# STATUS=completed
# VERSION=latest02
# END_TIME=18:34

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-19 18:34:19.051566422+00:00
start-sync_0 = 18:34:23
start-zstd = 18:34:27
start-sync_1 = 18:34:29
end-sync_1 = 18:34:33
end = 2021-11-19 18:34:33.850414864+00:00

[server]
name = docker
node = 4
repo = "cake233/test-hello-amd64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
