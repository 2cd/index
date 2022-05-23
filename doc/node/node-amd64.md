# node-amd64

## How to run it?

```sh
docker run \
    -it \
    --name node-amd64 \
    cake233/node-amd64
```

## How to exec shell?

```sh
docker exec -it node-amd64 bash
```

## node-amd64.toml

```toml
[main]
name = "node"
tag = ["latest", "2022-05-23"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_amd64_2022-05-23_12-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0053cd053d6be5f377fb5dbbedb8f74e392b110f488ec3ee52ff8a8f6d6b1bcc"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "997M"
tar_bytes = 1044583424

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "198M"
zstd_bytes = 207435098

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220509"
previous_tag = "2022-05-09"
previous_file = "node_amd64_2022-05-09_12-16-rootfs.tar.zst"
previous_sha256 = "ad8efd0528e9b2acc8fc723af0f0aae859e75391f297af81d2afea4d875dfde9"

current_version = "latest01"
current_date = "20220523"
old_file = "node_amd64_2022-04-25_12-12-rootfs.tar.zst"
old_sha256 = "c9b95e22e4423516d7f4baeeea41a2375300b60d16a3bfdf16924be3a3d2379b"
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node_amd64_2022-05-23_12-14-rootfs.tar.zst
# SHA256SUM=0053cd053d6be5f377fb5dbbedb8f74e392b110f488ec3ee52ff8a8f6d6b1bcc
# BUILD_DATE=20220523
# BUILD_TAG=2022-05-23
# STATUS=completed
# VERSION=latest01
# END_TIME=12:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-23
begin = 2022-05-23 12:02:32.004393602+00:00
start-sync_0 = 12:03:33
start-zstd = 12:05:39
start-sync_1 = 12:14:11
end-sync_1 = 12:14:30
end = 2022-05-23 12:14:30.753222375+00:00

[server]
repo = "cake233/node-amd64"

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
node = 'v18.2.0'
yarn = '1.22.19'
npm = '8.9.0'
```
