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
tag = ["latest", "2022-01-24"]
os = "ubuntu"
release = "lts"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "mongo_amd64_2022-01-24_12-09.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "d17665e3588eeefc3a026e2a984dd50815b3b7adbff670d9f22137ae6d813bed"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "905M"
tar_bytes = 948170240

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "178M"
zstd_bytes = 186572666

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220124"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=mongo_amd64
# ROOTFS_FILE=mongo_amd64_2022-01-24_12-09-rootfs.tar.zst
# SHA256SUM=d17665e3588eeefc3a026e2a984dd50815b3b7adbff670d9f22137ae6d813bed
# BUILD_DATE=20220124
# BUILD_TAG=2022-01-24
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-24
begin = 2022-01-24 12:02:27.913432723+00:00
start-sync_0 = 12:03:53
start-zstd = 12:04:29
start-sync_1 = 12:08:49
end-sync_1 = 12:09:06
end = 2022-01-24 12:09:06.555884569+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.31-0ubuntu9.2) 2.31'
gosu = '1.12 (go1.13.10 on linux/amd64; gc)'
jsyaml = '3.13.1'
mongo_major = '5.0'
mongo_version = '5.0.5'
```
