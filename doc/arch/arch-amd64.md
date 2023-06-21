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
tag = ["base", "2023-06-21"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch_amd64_2023-06-21_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c335b00ded489863580a8afd3536062e396cc77f2af0fad4289a3f1b7db97e95"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "989M"
tar_bytes = 1036389376

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "283M"
zstd_bytes = 296402259

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230621"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch_amd64_2023-06-21_00-06-rootfs.tar.zst
# SHA256SUM=c335b00ded489863580a8afd3536062e396cc77f2af0fad4289a3f1b7db97e95
# BUILD_DATE=20230621
# BUILD_TAG=2023-06-21
# STATUS=completed
# VERSION=latest01
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-21
begin = 2023-06-21 00:02:41.379874733+00:00
start-sync_0 = 00:04:26
start-zstd = 00:05:28
start-sync_1 = 00:06:01
end-sync_1 = 00:06:28
end = 2023-06-21 00:06:28.706363572+00:00

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
