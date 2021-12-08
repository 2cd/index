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
tag = ["latest", "2021-12-08"]
os = "ubuntu"
release = "lts"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "mongo_arm64_2021-12-08_01-13.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "d7ceadead9400329a49f83eeb9fa63a3435ede7edeed353c600725f06e2c57da"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "867M"
tar_bytes = 908447744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "173M"
zstd_bytes = 181174906

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211128"
last_tag = "2021-11-28"
last_file = "mongo_arm64_2021-11-28_23-08-rootfs.tar.zst"
last_sha256 = "ac42a14d5e52db223447591a7a8a380212a2a9ba8335c05bda04e22b9c6ad954"

current_version = "latest02"
current_date = "20211208"
old_file = "mongo_arm64+latest-2021_11-01-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=mongo_arm64
# ROOTFS_FILE=mongo_arm64_2021-12-08_01-13-rootfs.tar.zst
# SHA256SUM=d7ceadead9400329a49f83eeb9fa63a3435ede7edeed353c600725f06e2c57da
# BUILD_DATE=20211208
# BUILD_TAG=2021-12-08
# STATUS=completed
# VERSION=latest02
# END_TIME=01:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-08
begin = 2021-12-08 01:06:15.432680678+00:00
start-sync_0 = 01:09:25
start-zstd = 01:09:54
start-sync_1 = 01:12:54
end-sync_1 = 01:13:14
end = 2021-12-08 01:13:14.891151917+00:00

[server]
repo = "cake233/mongo-arm64"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
last = true
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
gosu = '1.12 (go1.13.10 on linux/arm64; gc)'
jsyaml = '3.13.1'
mongo_major = '5.0'
mongo_version = '5.0.5'
```
