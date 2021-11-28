# alpine-zsh-armv7

## How to run it?

```shell
docker run \
    -it \
    --name alpine-zsh-armv7 \
    cake233/alpine-zsh-armv7
```

## How to exec shell?

```shell
    docker exec -it alpine-zsh-armv7 zsh
```

## alpine-zsh-armv7.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2021-11-28"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "alpine-zsh-armv7_2021-11-28_20-55.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "114e5c33904ff7bc56ac33cd36524574d9b1c10824acf715667d1e61869169cf"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "73M"
tar_bytes = 76034048

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "25M"
zstd_bytes = 25906732

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211007"
last_tag = ""
last_file = "alpine-edge_armhf+zsh-2021_10-07-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211128"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-zsh-armv7_2021-11-28_20-55.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest02
# END_TIME=20:55

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 20:51:13.006129784+00:00
start-sync_0 = 20:53:58
start-zstd = 20:55:20
start-sync_1 = 20:55:41
end-sync_1 = 20:55:50
end = 2021-11-28 20:55:50.989028605+00:00

[server]
repo = "cake233/alpine-zsh-armv7"

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
