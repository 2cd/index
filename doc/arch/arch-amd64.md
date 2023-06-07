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
tag = ["base", "2023-06-07"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch_amd64_2023-06-07_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "374e6e5f6d6c2bb267783f719b941921222438cd339e989be0dd35227baced05"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "968M"
tar_bytes = 1014258176

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "276M"
zstd_bytes = 289080025

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230607"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch_amd64_2023-06-07_00-05-rootfs.tar.zst
# SHA256SUM=374e6e5f6d6c2bb267783f719b941921222438cd339e989be0dd35227baced05
# BUILD_DATE=20230607
# BUILD_TAG=2023-06-07
# STATUS=completed
# VERSION=latest01
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-07
begin = 2023-06-07 00:02:31.866157210+00:00
start-sync_0 = 00:04:00
start-zstd = 00:04:50
start-sync_1 = 00:05:20
end-sync_1 = 00:05:43
end = 2023-06-07 00:05:43.935926047+00:00

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
