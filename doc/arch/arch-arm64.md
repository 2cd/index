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
tag = ["base", "2022-12-07"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch_arm64_2022-12-07_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6842810c2eaf062b18bcff3e6d81eccfb6fa9d96f58da142f544fa5fa3fb3070"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "890M"
tar_bytes = 933217792

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "252M"
zstd_bytes = 263925453

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20221207"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch_arm64_2022-12-07_00-06-rootfs.tar.zst
# SHA256SUM=6842810c2eaf062b18bcff3e6d81eccfb6fa9d96f58da142f544fa5fa3fb3070
# BUILD_DATE=20221207
# BUILD_TAG=2022-12-07
# STATUS=completed
# VERSION=latest01
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-07
begin = 2022-12-07 00:02:22.944917653+00:00
start-sync_0 = 00:05:09
start-zstd = 00:05:52
start-sync_1 = 00:06:14
end-sync_1 = 00:06:35
end = 2022-12-07 00:06:35.486742750+00:00

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
