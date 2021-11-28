# node-alpine-arm64

## How to run it?

```shell
docker run \
    -it \
    --name node-alpine-arm64 \
    cake233/node-alpine-arm64
```

## How to exec shell?

```shell
    docker exec -it node-alpine-arm64 bash
```

## node-alpine-arm64.toml

```toml
[main]
name = "node"
tag = ["alpine", "2021-11-28", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "node-musl_arm64_2021-11-28_22-38.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "896a0f3932b90f0dc1ba70de9933d1069839e4988294ba4b2573f579fe2427a3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "179M"
tar_bytes = 187028992

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "33M"
zstd_bytes = 33605619

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211101"
last_tag = ""
last_file = "node_arm64+alpine-2021_11-01-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211128"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node-musl_arm64_2021-11-28_22-38.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest02
# END_TIME=22:38

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 22:36:59.456720959+00:00
start-sync_0 = 22:37:35
start-zstd = 22:37:43
start-sync_1 = 22:38:34
end-sync_1 = 22:38:41
end = 2021-11-28 22:38:41.527692050+00:00

[server]
repo = "cake233/node-alpine-arm64"

[server.node1]
name = "cn"
current = false
last = true
split = false

[server.node2]
name = "us"
current = false
last = true
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

[version]
node = 'v17.1.0'
yarn = '1.22.15'
npm = '8.1.2'
```
