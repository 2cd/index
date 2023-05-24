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
tag = ["base", "2023-05-24"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch_armhf_2023-05-24_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "28cb51bfe539303f952e6c3dd3d085193807667e3f95059603902fd6980fb8f9"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "807M"
tar_bytes = 845548032

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "239M"
zstd_bytes = 250003573

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230524"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch_armhf_2023-05-24_00-06-rootfs.tar.zst
# SHA256SUM=28cb51bfe539303f952e6c3dd3d085193807667e3f95059603902fd6980fb8f9
# BUILD_DATE=20230524
# BUILD_TAG=2023-05-24
# STATUS=completed
# VERSION=latest01
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-24
begin = 2023-05-24 00:02:30.173094682+00:00
start-sync_0 = 00:05:15
start-zstd = 00:05:59
start-sync_1 = 00:06:17
end-sync_1 = 00:06:38
end = 2023-05-24 00:06:38.158586289+00:00

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
