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
tag = ["base", "2023-02-01"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch_armhf_2023-02-01_00-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2bab63f2b61d80ce7a4860e40be05e63133ac975e1283656ed9f0c875f3065b4"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "805M"
tar_bytes = 843123712

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "239M"
zstd_bytes = 249708165

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230201"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch_armhf_2023-02-01_00-08-rootfs.tar.zst
# SHA256SUM=2bab63f2b61d80ce7a4860e40be05e63133ac975e1283656ed9f0c875f3065b4
# BUILD_DATE=20230201
# BUILD_TAG=2023-02-01
# STATUS=completed
# VERSION=latest01
# END_TIME=00:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-01
begin = 2023-02-01 00:02:27.543845143+00:00
start-sync_0 = 00:06:53
start-zstd = 00:07:38
start-sync_1 = 00:07:58
end-sync_1 = 00:08:21
end = 2023-02-01 00:08:21.045283203+00:00

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
