# mongo-amd64

## How to run it?

```sh
docker run \
    -it \
    --name mongo-amd64 \
    cake233/mongo-amd64
```

## How to exec shell?

```sh
docker exec -it mongo-amd64 bash
```

## mongo-amd64.toml

```toml
[main]
name = "mongo"
tag = ["latest", "2022-05-02"]
os = "ubuntu"
release = "lts"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "mongo_amd64_2022-05-02_12-19.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e91d0b232b234512fb3ca699cf1d8a0237eed7737aad68c63574d787bca9e76d"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "907M"
tar_bytes = 950761472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "163M"
zstd_bytes = 169965587

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220418"
previous_tag = "2022-04-18"
previous_file = "mongo_amd64_2022-04-18_12-09-rootfs.tar.zst"
previous_sha256 = "7fb8c78318fe50c0769c6dc97827dfb72956c44525701b3cbdf39d2a02bb9579"

current_version = "latest02"
current_date = "20220502"
old_file = "mongo_amd64_2022-04-04_11-08-rootfs.tar.zst"
old_sha256 = "4d8d105b097871be15517096fb49499a647c98ca114099bbb0b65e62083d038a"
# edition 2021
# DISTRO_NAME=mongo_amd64
# ROOTFS_FILE=mongo_amd64_2022-05-02_12-19-rootfs.tar.zst
# SHA256SUM=e91d0b232b234512fb3ca699cf1d8a0237eed7737aad68c63574d787bca9e76d
# BUILD_DATE=20220502
# BUILD_TAG=2022-05-02
# STATUS=completed
# VERSION=latest02
# END_TIME=12:19

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-02
begin = 2022-05-02 12:13:40.010321070+00:00
start-sync_0 = 12:14:22
start-zstd = 12:14:47
start-sync_1 = 12:19:15
end-sync_1 = 12:19:32
end = 2022-05-02 12:19:32.141523563+00:00

[server]
repo = "cake233/mongo-amd64"

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
gosu = '1.12 (go1.13.10 on linux/amd64; gc)'
jsyaml = '3.13.1'
mongo_major = '5.0'
mongo_version = '5.0.8'
```
