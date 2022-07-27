# arch-amd64

## How to run it?

```sh
docker run \
    -it \
    --name arch-amd64 \
    cake233/arch-amd64
```

## How to exec shell?

```sh
docker exec -it arch-amd64 sh
```

## arch-amd64.toml

```toml
[main]
name = "arch"
tag = ["base", "2022-07-27"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch_amd64_2022-07-27_00-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "815e9b437c0cd5131c73b0a65fd37d2b58808f9596c25996e677d59d63a111c4"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "906M"
tar_bytes = 949550592

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "258M"
zstd_bytes = 270375352

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220727"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch_amd64_2022-07-27_00-10-rootfs.tar.zst
# SHA256SUM=815e9b437c0cd5131c73b0a65fd37d2b58808f9596c25996e677d59d63a111c4
# BUILD_DATE=20220727
# BUILD_TAG=2022-07-27
# STATUS=completed
# VERSION=latest01
# END_TIME=00:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-27
begin = 2022-07-27 00:02:30.110058608+00:00
start-sync_0 = 00:08:30
start-zstd = 00:09:22
start-sync_1 = 00:09:48
end-sync_1 = 00:10:15
end = 2022-07-27 00:10:15.566277330+00:00

[server]
repo = "cake233/arch-amd64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = true
previous = false
in_sync = false
split = false

[server.node3]
name = "azure"
current = true
previous = false
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
