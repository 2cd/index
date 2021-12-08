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
tag = ["base", "2021-12-08"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "arch_armhf_2021-12-08_00-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "1bd54c102a9fda7cecf36a0e36780651b7009c60da801b44a28a1ea5c42af9ed"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "560M"
tar_bytes = 586338816

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "167M"
zstd_bytes = 174404793

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211128"
last_tag = ""
last_file = ""
last_sha256 = ""

current_version = "latest01"
current_date = "20211208"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch_armhf_2021-12-08_00-05-rootfs.tar.zst
# SHA256SUM=1bd54c102a9fda7cecf36a0e36780651b7009c60da801b44a28a1ea5c42af9ed
# BUILD_DATE=20211208
# BUILD_TAG=2021-12-08
# STATUS=completed
# VERSION=latest01
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-08
begin = 2021-12-08 00:02:29.245622371+00:00
start-sync_0 = 00:04:13
start-zstd = 00:05:06
start-sync_1 = 00:05:18
end-sync_1 = 00:05:41
end = 2021-12-08 00:05:41.660065517+00:00

[server]
repo = "cake233/arch-armv7"

[server.node1]
name = "cn"
current = false
last = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
last = false
in_sync = false
split = false

[server.node3]
name = "azure"
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
