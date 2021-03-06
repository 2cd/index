# oracle-arm64

## How to run it?

```sh
docker run \
    -it \
    --name oracle-arm64 \
    cake233/oracle-arm64
```

## How to exec shell?

```sh
docker exec -it oracle-arm64 sh
```

## oracle-arm64.toml

```toml
[main]
name = "oracle"
tag = ["base", "2022-06-15"]
os = "oracle"
release = "base"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "oracle_arm64_2022-06-15_00-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d22e2173b4bf0f40c0d8bd67c9d7c277d6bb44e3fd036e607814e95e73f19a05"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "469M"
tar_bytes = 491011072

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "72M"
zstd_bytes = 74611028

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220515"
previous_tag = "2022-05-15"
previous_file = "oracle_arm64_2022-05-15_00-09-rootfs.tar.zst"
previous_sha256 = "406caaf8a47284ac5693656d0d1de249db425673e18957675a620d65b396adb8"

current_version = "latest02"
current_date = "20220615"
old_file = "oracle_arm64_2022-04-26_02-43-rootfs.tar.zst"
old_sha256 = "e021ec160bacf5b0c455ef1590def708f87d5eddfdd0a5c138ab53870c1074c7"
# edition 2021
# DISTRO_NAME=oracle_arm64
# ROOTFS_FILE=oracle_arm64_2022-06-15_00-12-rootfs.tar.zst
# SHA256SUM=d22e2173b4bf0f40c0d8bd67c9d7c277d6bb44e3fd036e607814e95e73f19a05
# BUILD_DATE=20220615
# BUILD_TAG=2022-06-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-15
begin = 2022-06-15 00:04:17.786958097+00:00
start-sync_0 = 00:10:16
start-zstd = 00:10:42
start-sync_1 = 00:12:10
end-sync_1 = 00:12:24
end = 2022-06-15 00:12:24.495822610+00:00

[server]
repo = "cake233/oracle-arm64"

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
```
