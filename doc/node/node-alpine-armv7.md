# node-alpine-armv7

## How to run it?

```sh
docker run \
    -it \
    --name node-alpine-armv7 \
    cake233/node-alpine-armv7
```

## How to exec shell?

```sh
docker exec -it node-alpine-armv7 bash
```

## node-alpine-armv7.toml

```toml
[main]
name = "node"
tag = ["alpine", "2022-01-31", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "node-musl_armhf_2022-01-31_12-03.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "de5947e3df96d90e95857823b57731bdbb17dbf0638623b4fe5544abd1e663b9"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "167M"
tar_bytes = 174479360

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "32M"
zstd_bytes = 33240355

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220117"
previous_tag = "2022-01-17"
previous_file = "node-musl_armhf_2022-01-17_12-04-rootfs.tar.zst"
previous_sha256 = "a8a7954831f42954798e4f73b6e74d3a9f052446071cb90dc1d15da2b0c27991"

current_version = "latest02"
current_date = "20220131"
old_file = "node-musl_armhf_2022-01-03_12-03-rootfs.tar.zst"
old_sha256 = "9c7dadb67eab559ad94bbd250393c323e2853d546c8f6b177342c5f1ac73f3a8"
# edition 2021
# DISTRO_NAME=node_armhf
# ROOTFS_FILE=node-musl_armhf_2022-01-31_12-03-rootfs.tar.zst
# SHA256SUM=de5947e3df96d90e95857823b57731bdbb17dbf0638623b4fe5544abd1e663b9
# BUILD_DATE=20220131
# BUILD_TAG=2022-01-31
# STATUS=completed
# VERSION=latest02
# END_TIME=12:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-31
begin = 2022-01-31 12:02:27.080435271+00:00
start-sync_0 = 12:03:13
start-zstd = 12:03:23
start-sync_1 = 12:03:40
end-sync_1 = 12:03:49
end = 2022-01-31 12:03:49.091272950+00:00

[server]
repo = "cake233/node-alpine-armv7"

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
ldd = 'musl libc (armhf) Version 1.2.2'
node = 'v17.4.0'
yarn = '1.22.17'
npm = '8.3.1'
```
