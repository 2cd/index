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
tag = ["latest", "2022-05-02"]
os = "ubuntu"
release = "lts"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "mongo_arm64_2022-05-02_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7001a66c5b3afa722af5802afaa4e97d4144130abbc19460d29c970698f8c2d1"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "874M"
tar_bytes = 916051968

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "158M"
zstd_bytes = 164949934

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220418"
previous_tag = "2022-04-18"
previous_file = "mongo_arm64_2022-04-18_12-10-rootfs.tar.zst"
previous_sha256 = "76dfb23b5278041cdbc47a6a13b203a16fe71e3f47e033953896db4b0837a9ab"

current_version = "latest02"
current_date = "20220502"
old_file = "mongo_arm64_2022-04-04_11-11-rootfs.tar.zst"
old_sha256 = "5de3516db20a08006f8fac1afe2dc4d43df1f01f2797e9d7c7b81ce9b1cd8727"
# edition 2021
# DISTRO_NAME=mongo_arm64
# ROOTFS_FILE=mongo_arm64_2022-05-02_12-12-rootfs.tar.zst
# SHA256SUM=7001a66c5b3afa722af5802afaa4e97d4144130abbc19460d29c970698f8c2d1
# BUILD_DATE=20220502
# BUILD_TAG=2022-05-02
# STATUS=completed
# VERSION=latest02
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-02
begin = 2022-05-02 12:02:41.097549586+00:00
start-sync_0 = 12:06:35
start-zstd = 12:07:07
start-sync_1 = 12:11:59
end-sync_1 = 12:12:20
end = 2022-05-02 12:12:20.417139558+00:00

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
MONGO_PACKAGE = 'mongodb-org'
MONGO_REPO = 'repo.mongodb.org'

[version]
ldd = 'ldd (Ubuntu GLIBC 2.31-0ubuntu9.7) 2.31'
gosu = '1.12 (go1.13.10 on linux/arm64; gc)'
jsyaml = '3.13.1'
mongo_major = '5.0'
mongo_version = '5.0.8'
```
