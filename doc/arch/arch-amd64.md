# arch-amd64

## How to run it?

```sh
docker run \
    -it \
    --name arch-amd64 \
    cake233/arch-amd64
```

## How to exec shell?

```sh
docker exec -it arch-amd64 sh
```

## arch-amd64.toml

```toml
[main]
name = "arch"
tag = ["base", "2022-07-20"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch_amd64_2022-07-20_00-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "dfda335b75273ef42513ec1c13777941bbc5c4dc3861915387f5a15d1a11f35f"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "878M"
tar_bytes = 919867904

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "251M"
zstd_bytes = 262934143

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220720"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch_amd64_2022-07-20_00-11-rootfs.tar.zst
# SHA256SUM=dfda335b75273ef42513ec1c13777941bbc5c4dc3861915387f5a15d1a11f35f
# BUILD_DATE=20220720
# BUILD_TAG=2022-07-20
# STATUS=completed
# VERSION=latest01
# END_TIME=00:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-20
begin = 2022-07-20 00:02:34.092870484+00:00
start-sync_0 = 00:09:47
start-zstd = 00:10:38
start-sync_1 = 00:11:05
end-sync_1 = 00:11:30
end = 2022-07-20 00:11:30.406147122+00:00

[server]
repo = "cake233/arch-amd64"

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
