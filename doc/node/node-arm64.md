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
tag = ["latest", "2024-03-04"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_arm64_2024-03-04_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "03c31fc1c204993c2e6abab87fc99a5b7cc856f5cb2a575de03b2222e553a1ec"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1155277312

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "212M"
zstd_bytes = 221762557

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231120"
previous_tag = "2023-11-20"
previous_file = "node_arm64_2023-11-20_12-11-rootfs.tar.zst"
previous_sha256 = "eb08b0926b37ce25f20c6fe276588729b80a00dbfd2996c2a7ca6d64a5a8753b"

current_version = "latest01"
current_date = "20240304"
old_file = "node_arm64_2023-10-23_12-12-rootfs.tar.zst"
old_sha256 = "5f25fb70f40f6c3ce061762f04a1a0912c471259472d4a5b6aa5c42713219054"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node_arm64_2024-03-04_12-10-rootfs.tar.zst
# SHA256SUM=03c31fc1c204993c2e6abab87fc99a5b7cc856f5cb2a575de03b2222e553a1ec
# BUILD_DATE=20240304
# BUILD_TAG=2024-03-04
# STATUS=completed
# VERSION=latest01
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-03-04
begin = 2024-03-04 12:02:36.112789985+00:00
start-sync_0 = 12:05:23
start-zstd = 12:05:38
start-sync_1 = 12:10:18
end-sync_1 = 12:10:35
end = 2024-03-04 12:10:35.903767292+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u4) 2.36'
node = 'v21.6.2'
yarn = '1.22.19'
npm = '10.2.4'
```
