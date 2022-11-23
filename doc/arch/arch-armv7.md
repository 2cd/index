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
tag = ["base", "2022-11-23"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch_armhf_2022-11-23_00-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c0278818fd08d965cf6ce58241807c57d5ffee1470b0b45b617754b823df2227"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "795M"
tar_bytes = 833167872

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "236M"
zstd_bytes = 247318675

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20221123"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch_armhf_2022-11-23_00-07-rootfs.tar.zst
# SHA256SUM=c0278818fd08d965cf6ce58241807c57d5ffee1470b0b45b617754b823df2227
# BUILD_DATE=20221123
# BUILD_TAG=2022-11-23
# STATUS=completed
# VERSION=latest01
# END_TIME=00:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-23
begin = 2022-11-23 00:02:29.797767532+00:00
start-sync_0 = 00:06:01
start-zstd = 00:06:48
start-sync_1 = 00:07:13
end-sync_1 = 00:07:37
end = 2022-11-23 00:07:37.416283056+00:00

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
