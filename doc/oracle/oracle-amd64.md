# oracle-amd64

## How to run it?

```sh
docker run \
    -it \
    --name oracle-amd64 \
    cake233/oracle-amd64
```

## How to exec shell?

```sh
docker exec -it oracle-amd64 sh
```

## oracle-amd64.toml

```toml
[main]
name = "oracle"
tag = ["base", "2022-06-15"]
os = "oracle"
release = "base"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "oracle_amd64_2022-06-15_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8c63d228d319d7c27c1fc390dd25e196abb8839620450762cef74766030fe2d1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "438M"
tar_bytes = 459258880

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "73M"
zstd_bytes = 76103655

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220515"
previous_tag = "2022-05-15"
previous_file = "oracle_amd64_2022-05-15_00-07-rootfs.tar.zst"
previous_sha256 = "e3e7080a34f1d977688b10e3aa53cadfc8760e2bcae129f91d0bffce25f2c335"

current_version = "latest02"
current_date = "20220615"
old_file = "oracle_amd64_2022-04-26_02-40-rootfs.tar.zst"
old_sha256 = "ffb3efa3df2007b27200103c0b3efa22a68a6bbe5ee9210b46fb58d1910b8ecd"
# edition 2021
# DISTRO_NAME=oracle_amd64
# ROOTFS_FILE=oracle_amd64_2022-06-15_00-06-rootfs.tar.zst
# SHA256SUM=8c63d228d319d7c27c1fc390dd25e196abb8839620450762cef74766030fe2d1
# BUILD_DATE=20220615
# BUILD_TAG=2022-06-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-15
begin = 2022-06-15 00:04:16.978839594+00:00
start-sync_0 = 00:05:05
start-zstd = 00:05:26
start-sync_1 = 00:06:44
end-sync_1 = 00:06:56
end = 2022-06-15 00:06:56.675618594+00:00

[server]
repo = "cake233/oracle-amd64"

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
