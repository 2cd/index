# alpine-zsh-amd64

## How to run it?

```shell
docker run \
    -it \
    --name alpine-zsh-amd64 \
    cake233/alpine-zsh-amd64
```

## How to exec shell?

```shell
    docker exec -it alpine-zsh-amd64 zsh
```

## alpine-zsh-amd64.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2021-11-28"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "alpine-zsh-amd64_2021-11-28_10-47.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "56cbea8d0ca1ab50375c1cf3230fede95a0d7de310e32154636a3d8a6e26ccaa"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "90M"
tar_bytes = 93686272

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "30M"
zstd_bytes = 31233289

[compatibility]
compatible_mode = true
current_version = "latest02"
current_date = 20211128
last_version = "latest01"
last_date = 20211109
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-zsh-amd64_2021-11-28_10-47.tar.zst
# BUILD_DATE=20211128
# STATUS=completed
# VERSION=latest02
# END_TIME=10:47

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-28 10:43:37.587326943+00:00
start-sync_0 = 10:46:23
start-zstd = 10:47:45
start-sync_1 = 10:47:50
end-sync_1 = 10:47:56
end = 2021-11-28 10:47:56.565587252+00:00

[server]
repo = "cake233/alpine-zsh-amd64"

[server.node1]
name = "cn"
current = false
last = true
split = false

[server.node2]
name = "us"
current = false
last = false
split = false
part = 12

[server.node3]
name = "global"
current = false
last = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "C.UTF-8"
```
