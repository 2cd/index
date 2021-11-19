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

## build info

```toml
[main]
name = "alpine"
tag = ["zsh", "2021-11-19"]
os = "alpine"
release = "edge"
arch = "amd64"
nogui = true

# If the value is false, then the container will not be downloaded.
completed = true

[file]
name = "alpine-zsh-amd64_2021-11-19_22-20.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "d54f7a1e2496f76deeff61a9112d904666b225fb91061fc4ce17071a554be9de"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "93M"
tar-bytes = 96668672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "32M"
zstd-bytes = 33012024

[compatibility]
compatible_mode = true
rootfs_version = "latest02"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-zsh-amd64_2021-11-19_22-20.tar.zst
# BUILD_DATE=20211119
# STATUS=completed
# VERSION=latest02
# END_TIME=22:20

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-19 22:17:16.665084216+00:00
start-sync_0 = 22:17:54
start-zstd = 22:20:15
start-sync_1 = 22:20:21
end-sync_1 = 22:20:28
end = 2021-11-19 22:20:28.151114167+00:00

[server]
name = "docker"
node = 4
repo = "cake233/alpine-zsh-amd64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
