# arch-arm64

## How to run it?

```sh
docker run \
    -it \
    --name arch-arm64 \
    cake233/arch-arm64
```

## How to exec shell?

```sh
docker exec -it arch-arm64 sh
```

## arch-arm64.toml

```toml
[main]
name = "arch"
tag = ["base", "2024-01-24"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch_arm64_2024-01-24_00-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8a6afcbe017b65a1b0d50ac66507e31779a22845394361141378dcda3c1819ae"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "921M"
tar_bytes = 965161472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "260M"
zstd_bytes = 272350526

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20240124"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch_arm64_2024-01-24_00-08-rootfs.tar.zst
# SHA256SUM=8a6afcbe017b65a1b0d50ac66507e31779a22845394361141378dcda3c1819ae
# BUILD_DATE=20240124
# BUILD_TAG=2024-01-24
# STATUS=completed
# VERSION=latest01
# END_TIME=00:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-24
begin = 2024-01-24 00:02:30.247098115+00:00
start-sync_0 = 00:06:54
start-zstd = 00:07:34
start-sync_1 = 00:07:50
end-sync_1 = 00:08:06
end = 2024-01-24 00:08:06.170470794+00:00

[server]
repo = "cake233/arch-arm64"

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
