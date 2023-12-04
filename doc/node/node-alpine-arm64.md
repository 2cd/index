# node-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name node-alpine-arm64 \
    cake233/node-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it node-alpine-arm64 bash
```

## node-alpine-arm64.toml

```toml
[main]
name = "node"
tag = ["alpine", "2023-12-04", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_arm64_2023-12-04_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f582c8215720f782aa6284021b7e81bc0f09167383fe2a102beb7143bab61b40"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "158M"
tar_bytes = 164935168

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "36M"
zstd_bytes = 37155749

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231023"
previous_tag = "2023-10-23"
previous_file = "node-musl_arm64_2023-10-23_12-05-rootfs.tar.zst"
previous_sha256 = "123994cce40a50577060636bf3f55c99a4d8f1feddb7eab69e3eea161f8d01b8"

current_version = "latest02"
current_date = "20231204"
old_file = "node-musl_arm64_2023-10-09_12-06-rootfs.tar.zst"
old_sha256 = "f60189e6be1c7abe38179f636f54dff29efa41d7a3c94c227e93bb795b87f52f"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node-musl_arm64_2023-12-04_12-04-rootfs.tar.zst
# SHA256SUM=f582c8215720f782aa6284021b7e81bc0f09167383fe2a102beb7143bab61b40
# BUILD_DATE=20231204
# BUILD_TAG=2023-12-04
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-04
begin = 2023-12-04 12:02:32.765907899+00:00
start-sync_0 = 12:03:44
start-zstd = 12:03:50
start-sync_1 = 12:04:52
end-sync_1 = 12:04:59
end = 2023-12-04 12:04:59.466840973+00:00

[server]
repo = "cake233/node-alpine-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.4'
node = 'v21.3.0'
yarn = '1.22.19'
npm = '10.2.4'
```
