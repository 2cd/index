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
tag = ["base", "2022-04-22"]
os = "oracle"
release = "base"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "oracle_amd64_2022-04-22_09-50.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4af864988d65f0a4e7f4fb278bec35a8989b6ca35890ace96cb5ab5d664cd6e5"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "448M"
tar_bytes = 468804096

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "74M"
zstd_bytes = 77560130

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220422"
previous_tag = "2022-04-22"
previous_file = "oracle_amd64_2022-04-22_04-14-rootfs.tar.zst"
previous_sha256 = "3b2508890a918c8506947e74255fef3666a556e5cb54f7b4aeffa95d302ec6a0"

current_version = "latest02"
current_date = "20220422"
old_file = "oracle_amd64_2022-04-22_05-55-rootfs.tar.zst"
old_sha256 = "a6ea2057cdf5ace9e30cb526dc64572ccd88fa5b4120bd0479f2676878ab109e"
# edition 2021
# DISTRO_NAME=oracle_amd64
# ROOTFS_FILE=oracle_amd64_2022-04-22_09-50-rootfs.tar.zst
# SHA256SUM=4af864988d65f0a4e7f4fb278bec35a8989b6ca35890ace96cb5ab5d664cd6e5
# BUILD_DATE=20220422
# BUILD_TAG=2022-04-22
# STATUS=completed
# VERSION=latest02
# END_TIME=09:50

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-22
begin = 2022-04-22 09:47:38.284266300+00:00
start-sync_0 = 09:48:32
start-zstd = 09:48:51
start-sync_1 = 09:50:09
end-sync_1 = 09:50:18
end = 2022-04-22 09:50:18.488460443+00:00

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
```
