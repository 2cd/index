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
tag = ["base", "2023-06-28"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch_armhf_2023-06-28_00-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b0fe563afd2f2584e7b9807b61122179536fb17f751d536ffdcb88420d0af8b7"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "817M"
tar_bytes = 856399872

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "242M"
zstd_bytes = 253455775

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230628"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch_armhf_2023-06-28_00-07-rootfs.tar.zst
# SHA256SUM=b0fe563afd2f2584e7b9807b61122179536fb17f751d536ffdcb88420d0af8b7
# BUILD_DATE=20230628
# BUILD_TAG=2023-06-28
# STATUS=completed
# VERSION=latest01
# END_TIME=00:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-28
begin = 2023-06-28 00:02:26.851681207+00:00
start-sync_0 = 00:06:10
start-zstd = 00:06:54
start-sync_1 = 00:07:12
end-sync_1 = 00:07:34
end = 2023-06-28 00:07:34.863612256+00:00

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
