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
tag = ["alpine", "2024-03-04", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_arm64_2024-03-04_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b58a66cc96b822db1945fe84eb2e40c2dbfa9e7b1977c1b9e1c5b72e7f1e8619"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "159M"
tar_bytes = 166039552

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "36M"
zstd_bytes = 37503149

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231023"
previous_tag = "2023-10-23"
previous_file = "node-musl_arm64_2023-10-23_12-05-rootfs.tar.zst"
previous_sha256 = "123994cce40a50577060636bf3f55c99a4d8f1feddb7eab69e3eea161f8d01b8"

current_version = "latest02"
current_date = "20240304"
old_file = "node-musl_arm64_2023-10-09_12-06-rootfs.tar.zst"
old_sha256 = "f60189e6be1c7abe38179f636f54dff29efa41d7a3c94c227e93bb795b87f52f"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node-musl_arm64_2024-03-04_12-04-rootfs.tar.zst
# SHA256SUM=b58a66cc96b822db1945fe84eb2e40c2dbfa9e7b1977c1b9e1c5b72e7f1e8619
# BUILD_DATE=20240304
# BUILD_TAG=2024-03-04
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-03-04
begin = 2024-03-04 12:02:32.226931433+00:00
start-sync_0 = 12:03:18
start-zstd = 12:03:24
start-sync_1 = 12:04:30
end-sync_1 = 12:04:36
end = 2024-03-04 12:04:36.883406459+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.4_git20230717'
node = 'v21.6.2'
yarn = '1.22.19'
npm = '10.2.4'
```
