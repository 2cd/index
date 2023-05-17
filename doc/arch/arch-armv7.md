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
tag = ["base", "2023-05-17"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch_armhf_2023-05-17_00-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b3a738c9d60a70d15de8c7cd83683d482d42f37a4350598e343d5093385662d5"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "807M"
tar_bytes = 845218816

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "239M"
zstd_bytes = 249931702

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230517"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch_armhf_2023-05-17_00-10-rootfs.tar.zst
# SHA256SUM=b3a738c9d60a70d15de8c7cd83683d482d42f37a4350598e343d5093385662d5
# BUILD_DATE=20230517
# BUILD_TAG=2023-05-17
# STATUS=completed
# VERSION=latest01
# END_TIME=00:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-17
begin = 2023-05-17 00:02:38.938770356+00:00
start-sync_0 = 00:08:51
start-zstd = 00:09:46
start-sync_1 = 00:10:14
end-sync_1 = 00:10:41
end = 2023-05-17 00:10:41.634028124+00:00

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
