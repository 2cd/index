# arch-armv7

## How to run it?

```shell
docker run \
    -it \
    --name arch-armv7 \
    cake233/arch-armv7
```

## How to exec shell?

```shell
    docker exec -it arch-armv7 sh
```

## arch-armv7.toml

```toml
[main]
name = "arch"
tag = ["base", "2021-12-01"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "arch_armhf_2021-12-01_00-04.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "b05f40eed7f7a8bb423e653521579c816f65cf8613100b73d988786dddb0cf66"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "560M"
tar_bytes = 586332672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "167M"
zstd_bytes = 174413298

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211128"
last_tag = ""
last_file = ""

current_version = "latest01"
current_date = "20211201"
old_file = ""
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch_armhf_2021-12-01_00-04-rootfs.tar.zst
# BUILD_DATE=20211201
# BUILD_TAG=2021-12-01
# STATUS=completed
# VERSION=latest01
# END_TIME=00:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-01
begin = 2021-12-01 00:01:52.961616831+00:00
start-sync_0 = 00:03:31
start-zstd = 00:04:22
start-sync_1 = 00:04:34
end-sync_1 = 00:04:55
end = 2021-12-01 00:04:55.414247375+00:00

[server]
repo = "cake233/arch-armv7"

[server.node1]
name = "cn"
current = false
last = false
in_sync = false
split = false

[server.node2]
name = "us"
current = false
last = false
in_sync = false
split = false

[server.node3]
name = "global"
current = false
last = false
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
