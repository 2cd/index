# node-arm64

## How to run it?

```sh
docker run \
    -it \
    --name node-arm64 \
    cake233/node-arm64
```

## How to exec shell?

```sh
docker exec -it node-arm64 bash
```

## node-arm64.toml

```toml
[main]
name = "node"
tag = ["latest", "2023-01-30"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_arm64_2023-01-30_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "91658551bdf67b8cd8287cca9544faf2e09d821ac4ffe881fc07f9d7edc1405e"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "952M"
tar_bytes = 997492224

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "198M"
zstd_bytes = 207295317

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230116"
previous_tag = "2023-01-16"
previous_file = "node_arm64_2023-01-16_12-11-rootfs.tar.zst"
previous_sha256 = "70d56e2c15f18bc52ef9aafca1d0d5d7fae2acf9058e5af5d239e7000b8894e7"

current_version = "latest02"
current_date = "20230130"
old_file = "node_arm64_2023-01-02_12-10-rootfs.tar.zst"
old_sha256 = "3314902da305111995d65148610bef6fcedd3fa8f39ea750d8396919e2cc83c3"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node_arm64_2023-01-30_12-10-rootfs.tar.zst
# SHA256SUM=91658551bdf67b8cd8287cca9544faf2e09d821ac4ffe881fc07f9d7edc1405e
# BUILD_DATE=20230130
# BUILD_TAG=2023-01-30
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-30
begin = 2023-01-30 12:02:36.971145583+00:00
start-sync_0 = 12:05:56
start-zstd = 12:06:16
start-sync_1 = 12:10:39
end-sync_1 = 12:10:59
end = 2023-01-30 12:10:59.041810366+00:00

[server]
repo = "cake233/node-arm64"

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
node = 'v19.5.0'
yarn = '1.22.19'
npm = '9.3.1'
```
