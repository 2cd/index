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
tag = ["latest", "2023-09-11"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_arm64_2023-09-11_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6338080a3dfd60915656192ccd8007bfe20b698e31cf240422db40cdfaa74e63"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1150147072

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "211M"
zstd_bytes = 220442992

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230828"
previous_tag = "2023-08-28"
previous_file = "node_arm64_2023-08-28_12-11-rootfs.tar.zst"
previous_sha256 = "0a257a39a381f9aed8dd88d2b420405766a093e3a1fb15e2467cdb302bdd7fe2"

current_version = "latest02"
current_date = "20230911"
old_file = "node_arm64_2023-08-14_12-12-rootfs.tar.zst"
old_sha256 = "eaaed66bb70342a30c17c0ee50a2af86029e611e94129cfa61c2d026fb9c872b"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node_arm64_2023-09-11_12-12-rootfs.tar.zst
# SHA256SUM=6338080a3dfd60915656192ccd8007bfe20b698e31cf240422db40cdfaa74e63
# BUILD_DATE=20230911
# BUILD_TAG=2023-09-11
# STATUS=completed
# VERSION=latest02
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-11
begin = 2023-09-11 12:02:40.481602117+00:00
start-sync_0 = 12:05:46
start-zstd = 12:06:02
start-sync_1 = 12:12:04
end-sync_1 = 12:12:26
end = 2023-09-11 12:12:26.622948952+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u1) 2.36'
node = 'v20.6.0'
yarn = '1.22.19'
npm = '9.8.1'
```
