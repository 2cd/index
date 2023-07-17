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
tag = ["alpine", "2023-07-17", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_amd64_2023-07-17_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8fce579edaa31ae39da200c63ea6b77287398eb256919d4fea12505d3b0fd908"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "192M"
tar_bytes = 201121280

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "35M"
zstd_bytes = 36443841

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230703"
previous_tag = "2023-07-03"
previous_file = "node-musl_amd64_2023-07-03_12-04-rootfs.tar.zst"
previous_sha256 = "9c9b166c070fdfa5d60bd8e7f06641f854dc2f554e0df14016e690a63d924505"

current_version = "latest01"
current_date = "20230717"
old_file = "node-musl_amd64_2023-06-19_12-05-rootfs.tar.zst"
old_sha256 = "649121a3168432357fda548e98c02d88b7ebe8274da88ef94a6004b235726aa6"
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node-musl_amd64_2023-07-17_12-05-rootfs.tar.zst
# SHA256SUM=8fce579edaa31ae39da200c63ea6b77287398eb256919d4fea12505d3b0fd908
# BUILD_DATE=20230717
# BUILD_TAG=2023-07-17
# STATUS=completed
# VERSION=latest01
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-17
begin = 2023-07-17 12:02:40.129426397+00:00
start-sync_0 = 12:03:39
start-zstd = 12:03:53
start-sync_1 = 12:05:16
end-sync_1 = 12:05:27
end = 2023-07-17 12:05:27.679923684+00:00

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
node = 'v20.4.0'
yarn = '1.22.19'
npm = '9.7.2'
```
