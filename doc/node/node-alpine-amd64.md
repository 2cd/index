# node-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name node-alpine-amd64 \
    cake233/node-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it node-alpine-amd64 bash
```

## node-alpine-amd64.toml

```toml
[main]
name = "node"
tag = ["alpine", "2023-12-04", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_amd64_2023-12-04_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "139c8b0bfed0e0b260964ed9e8e49619c249cff685b9330573c2f144c25f6a0e"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "153M"
tar_bytes = 159652864

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "36M"
zstd_bytes = 37615953

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231120"
previous_tag = "2023-11-20"
previous_file = "node-musl_amd64_2023-11-20_12-05-rootfs.tar.zst"
previous_sha256 = "b3d4429eb22a4bcd975af5bd44ef864b9c1dd7742bd9b81cb6d693e7dd5a2f26"

current_version = "latest02"
current_date = "20231204"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node-musl_amd64_2023-12-04_12-05-rootfs.tar.zst
# SHA256SUM=139c8b0bfed0e0b260964ed9e8e49619c249cff685b9330573c2f144c25f6a0e
# BUILD_DATE=20231204
# BUILD_TAG=2023-12-04
# STATUS=completed
# VERSION=latest02
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-04
begin = 2023-12-04 12:02:36.943156346+00:00
start-sync_0 = 12:04:24
start-zstd = 12:04:34
start-sync_1 = 12:05:37
end-sync_1 = 12:05:46
end = 2023-12-04 12:05:46.816791147+00:00

[server]
repo = "cake233/node-alpine-amd64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = true
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = true
previous = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (x86_64) Version 1.2.4'
node = 'v21.3.0'
yarn = '1.22.19'
npm = '10.2.4'
```
