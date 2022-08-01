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
tag = ["alpine", "2022-08-01", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_arm64_2022-08-01_12-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "64359b7ba6684b43764e32812128b95023d471230de11f51f3234296c391a435"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "175M"
tar_bytes = 182905344

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "33M"
zstd_bytes = 33612682

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220704"
previous_tag = "2022-07-04"
previous_file = "node-musl_arm64_2022-07-04_12-04-rootfs.tar.zst"
previous_sha256 = "da0ea73b31b2c40ff49abb68f41231301bb2fcc1a081cda9f4f3e49223e09940"

current_version = "latest02"
current_date = "20220801"
old_file = "node-musl_arm64_2022-06-20_12-04-rootfs.tar.zst"
old_sha256 = "8838f9e316cb8dd0e0c67770534e2d0492c424ec8e7fd4b05dcb86b1bcfff244"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node-musl_arm64_2022-08-01_12-06-rootfs.tar.zst
# SHA256SUM=64359b7ba6684b43764e32812128b95023d471230de11f51f3234296c391a435
# BUILD_DATE=20220801
# BUILD_TAG=2022-08-01
# STATUS=completed
# VERSION=latest02
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-01
begin = 2022-08-01 12:02:44.510592534+00:00
start-sync_0 = 12:04:36
start-zstd = 12:04:50
start-sync_1 = 12:06:05
end-sync_1 = 12:06:17
end = 2022-08-01 12:06:17.710777604+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.3'
node = 'v18.7.0'
yarn = '1.22.19'
npm = '8.15.0'
```
