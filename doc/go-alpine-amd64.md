# go-alpine-amd64

## How to run it?

```shell
docker run \
    -it \
    --name go-alpine-amd64 \
    cake233/go-alpine-amd64
```

## How to exec shell?

```shell
    docker exec -it go-alpine-amd64 bash
```

## build info

```toml
[main]
name = "go"
tag = ["alpine", "2021-11-27", "musl-libc"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
nogui = true

# If the value is false, then the container will not be downloaded.
completed = true

[file]
name = "go-alpine-amd64_2021-11-27_18-57.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "c2d5e7aebd815f7de145920950dfd8d64dc3cbdc8f73cbbb2019230015a803d3"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "323M"
tar-bytes = 338339328

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "98M"
zstd-bytes = 102102997

[compatibility]
compatible_mode = true
rootfs_version = "latest02"
# edition 2021
# DISTRO_NAME=alpine-stable_amd64
# ROOTFS_FILE=go-alpine-amd64_2021-11-27_18-57.tar.zst
# BUILD_DATE=20211127
# STATUS=completed
# VERSION=latest02
# END_TIME=18:57

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-27 18:56:18.135657034+00:00
start-sync_0 = 18:56:40
start-zstd = 18:56:48
start-sync_1 = 18:57:03
end-sync_1 = 18:57:15
end = 2021-11-27 18:57:15.732733354+00:00

[server]
name = "docker"
node = 4
repo = "cake233/go-alpine-amd64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
export PATH="/go/bin:/usr/local/go/bin${PATH:+:${PATH}}"
export GOPATH="/go"

[version]
go = 'go version go1.17.3 linux/amd64'

[other]
workdir = "/go"
```
