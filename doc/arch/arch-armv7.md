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
tag = ["base", "2022-08-31"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch_armhf_2022-08-31_00-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "944d7bd9c91f5329cccb0378a4473fe0c984ce7b8e05f42c4637a88c13095bf0"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "771M"
tar_bytes = 808015872

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "231M"
zstd_bytes = 241274662

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220831"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch_armhf_2022-08-31_00-14-rootfs.tar.zst
# SHA256SUM=944d7bd9c91f5329cccb0378a4473fe0c984ce7b8e05f42c4637a88c13095bf0
# BUILD_DATE=20220831
# BUILD_TAG=2022-08-31
# STATUS=completed
# VERSION=latest01
# END_TIME=00:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-31
begin = 2022-08-31 00:02:20.435553945+00:00
start-sync_0 = 00:12:41
start-zstd = 00:13:21
start-sync_1 = 00:13:40
end-sync_1 = 00:14:00
end = 2022-08-31 00:14:00.343734099+00:00

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
