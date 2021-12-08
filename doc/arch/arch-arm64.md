# arch-arm64

## How to run it?

```shell
docker run \
    -it \
    --name arch-arm64 \
    cake233/arch-arm64
```

## How to exec shell?

```shell
    docker exec -it arch-arm64 sh
```

## arch-arm64.toml

```toml
[main]
name = "arch"
tag = ["base", "2021-12-08"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "arch_arm64_2021-12-08_00-04.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "49c90bf707f803539ffea21ac6a108381185135ab63f33dc23b0907d70156304"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "641M"
tar_bytes = 671763456

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "177M"
zstd_bytes = 184910748

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
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch_arm64_2021-12-08_00-04-rootfs.tar.zst
# SHA256SUM=49c90bf707f803539ffea21ac6a108381185135ab63f33dc23b0907d70156304
# BUILD_DATE=20211208
# BUILD_TAG=2021-12-08
# STATUS=completed
# VERSION=latest01
# END_TIME=00:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-08
begin = 2021-12-08 00:02:23.305112542+00:00
start-sync_0 = 00:03:43
start-zstd = 00:04:27
start-sync_1 = 00:04:39
end-sync_1 = 00:04:55
end = 2021-12-08 00:04:55.966783959+00:00

[server]
repo = "cake233/arch-arm64"

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
