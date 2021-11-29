# mongo-arm64

## How to run it?

```shell
docker run \
    -it \
    --name mongo-arm64 \
    cake233/mongo-arm64
```

## How to exec shell?

```shell
    docker exec -it mongo-arm64 bash
```

## mongo-arm64.toml

```toml
[main]
name = "mongo"
tag = ["latest", "2021-11-28"]
os = "ubuntu"
release = "lts"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "mongo_arm64_2021-11-28_23-08.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "157144ec3ea0b8aa41e714469338d6728acffb7418d70b686aa0a04a96104783"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "867M"
tar_bytes = 908549120

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "173M"
zstd_bytes = 181133127

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211101"
last_tag = ""
last_file = "mongo_arm64+latest-2021_11-01-rootfs.tar.zst"

current_version = "latest01"
current_date = "20211128"
# edition 2021
# DISTRO_NAME=mongo_arm64
# ROOTFS_FILE=mongo_arm64_2021-11-28_23-08-rootfs.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest01
# END_TIME=23:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 22:59:20.375379952+00:00
start-sync_0 = 23:03:16
start-zstd = 23:03:46
start-sync_1 = 23:07:43
end-sync_1 = 23:08:00
end = 2021-11-28 23:08:00.424882678+00:00

[server]
repo = "cake233/mongo-arm64"

[server.node1]
name = "cn"
current = false
last = true
split = false

[server.node2]
name = "us"
current = false
last = true
split = false
part = 12

[server.node3]
name = "global"
current = false
last = true
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
gosu = '1.12 (go1.13.10 on linux/arm64; gc)'
jsyaml = '3.13.1'
mongo_major = '5.0'
mongo_version = '5.0.4'
```
