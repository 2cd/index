# arch-armv7

## How to run it?

```sh
docker run \
    -it \
    --name arch-armv7 \
    cake233/arch-armv7
```

## How to exec shell?

```sh
docker exec -it arch-armv7 sh
```

## arch-armv7.toml

```toml
[main]
name = "arch"
tag = ["base", "2022-01-26"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "arch_armhf_2022-01-26_00-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "1eb6772281b21527137f3aaaead95151e72270e787a2b6e0e63b9a6671a152b7"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "561M"
tar_bytes = 587397632

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "168M"
zstd_bytes = 175291173

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220126"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch_armhf_2022-01-26_00-05-rootfs.tar.zst
# SHA256SUM=1eb6772281b21527137f3aaaead95151e72270e787a2b6e0e63b9a6671a152b7
# BUILD_DATE=20220126
# BUILD_TAG=2022-01-26
# STATUS=completed
# VERSION=latest01
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-26
begin = 2022-01-26 00:02:34.314885596+00:00
start-sync_0 = 00:03:51
start-zstd = 00:04:32
start-sync_1 = 00:04:47
end-sync_1 = 00:05:06
end = 2022-01-26 00:05:06.338574501+00:00

[server]
repo = "cake233/arch-armv7"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = false
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
