# mongo-arm64

## How to run it?

```sh
docker run \
    -it \
    --name mongo-arm64 \
    cake233/mongo-arm64
```

## How to exec shell?

```sh
docker exec -it mongo-arm64 bash
```

## mongo-arm64.toml

```toml
[main]
name = "mongo"
tag = ["latest", "2022-04-04"]
os = "ubuntu"
release = "lts"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "mongo_arm64_2022-04-04_11-11.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "5de3516db20a08006f8fac1afe2dc4d43df1f01f2797e9d7c7b81ce9b1cd8727"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "873M"
tar_bytes = 914664960

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "158M"
zstd_bytes = 164750855

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220321"
previous_tag = "2022-03-21"
previous_file = "mongo_arm64_2022-03-21_12-10-rootfs.tar.zst"
previous_sha256 = "df2e1dae19b7945ef573a8a12fe24a2bf95b26de51f3eef7ad37ff91986680bf"

current_version = "latest02"
current_date = "20220404"
old_file = "mongo_arm64_2022-03-07_12-10-rootfs.tar.zst"
old_sha256 = "38151c1a0eb1240720522df5cb7025eef0694ba2a77c650423c0a5ee0cd6796a"
# edition 2021
# DISTRO_NAME=mongo_arm64
# ROOTFS_FILE=mongo_arm64_2022-04-04_11-11-rootfs.tar.zst
# SHA256SUM=5de3516db20a08006f8fac1afe2dc4d43df1f01f2797e9d7c7b81ce9b1cd8727
# BUILD_DATE=20220404
# BUILD_TAG=2022-04-04
# STATUS=completed
# VERSION=latest02
# END_TIME=11:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-04
begin = 2022-04-04 11:02:35.288283066+00:00
start-sync_0 = 11:06:25
start-zstd = 11:06:58
start-sync_1 = 11:11:34
end-sync_1 = 11:11:54
end = 2022-04-04 11:11:54.661421369+00:00

[server]
repo = "cake233/mongo-arm64"

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
LANG = "en_US.UTF-8"
MONGO_PACKAGE = 'mongodb-org'
MONGO_REPO = 'repo.mongodb.org'

[version]
ldd = 'ldd (Ubuntu GLIBC 2.31-0ubuntu9.7) 2.31'
gosu = '1.12 (go1.13.10 on linux/arm64; gc)'
jsyaml = '3.13.1'
mongo_major = '5.0'
mongo_version = '5.0.6'
```
