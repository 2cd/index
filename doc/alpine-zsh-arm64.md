# alpine-zsh-arm64

## How to run it?

```shell
docker run \
    -it \
    --name alpine-zsh-arm64 \
    cake233/alpine-zsh-arm64
```

## How to exec shell?

```shell
    docker exec -it alpine-zsh-arm64 zsh
```

## alpine-zsh-arm64.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2021-11-28"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "alpine-zsh-arm64_2021-11-28_16-59.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "d2215eee08b0f22ef4a59bf6f615b396304b5c07ed6b3bebf9893ea15110f6ab"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "91M"
tar_bytes = 94794752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "30M"
zstd_bytes = 31400927

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211109"
last_tag = ""
last_file = "alpine-edge_arm64+zsh-2021_11-09-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211128"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-zsh-arm64_2021-11-28_16-59.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest02
# END_TIME=16:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 16:53:23.569101717+00:00
start-sync_0 = 16:57:27
start-zstd = 16:58:50
start-sync_1 = 16:58:55
end-sync_1 = 16:59:01
end = 2021-11-28 16:59:01.472339799+00:00

[server]
repo = "cake233/alpine-zsh-arm64"

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
last = true
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "C.UTF-8"
```
