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
tag = ["alpine", "2022-03-14", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "node-musl_amd64_2022-03-14_12-04.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "e384942d09c08c65d648820863283e8b1a2d7b02073200433a01da2f80b964c6"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "180M"
tar_bytes = 188271104

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "32M"
zstd_bytes = 32886179

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220301"
previous_tag = "2022-03-01"
previous_file = "node-musl_amd64_2022-03-01_18-55-rootfs.tar.zst"
previous_sha256 = "7879f26644621eeb3ef67cde51ccca6902d8565a67c789bda67bc4e56977814a"

current_version = "latest01"
current_date = "20220314"
old_file = "node-musl_amd64_2022-02-14_12-03-rootfs.tar.zst"
old_sha256 = "7a22cc88c8634c41094d836c91eef01c9742a9059b1a5efd7835530b761a5f3e"
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node-musl_amd64_2022-03-14_12-04-rootfs.tar.zst
# SHA256SUM=e384942d09c08c65d648820863283e8b1a2d7b02073200433a01da2f80b964c6
# BUILD_DATE=20220314
# BUILD_TAG=2022-03-14
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-14
begin = 2022-03-14 12:02:33.005666799+00:00
start-sync_0 = 12:03:22
start-zstd = 12:03:37
start-sync_1 = 12:04:47
end-sync_1 = 12:04:59
end = 2022-03-14 12:04:59.657830075+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'musl libc (x86_64) Version 1.2.2'
node = 'v17.7.1'
yarn = '1.22.17'
npm = '8.5.2'
```
