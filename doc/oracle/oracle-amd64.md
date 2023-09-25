# oracle-amd64

## How to run it?

```sh
docker run \
    -it \
    --name oracle-amd64 \
    cake233/oracle-amd64
```

## How to exec shell?

```sh
docker exec -it oracle-amd64 sh
```

## oracle-amd64.toml

```toml
[main]
name = "oracle"
tag = ["base", "2023-03-15"]
os = "oracle"
release = "base"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "oracle_amd64_2023-03-15_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3d8037dddf83aac07df7a30a0ae423548b23a8398c8d559a101a9437681722af"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "447M"
tar_bytes = 468089344

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "76M"
zstd_bytes = 79654664

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230215"
previous_tag = "2023-02-15"
previous_file = "oracle_amd64_2023-02-15_00-06-rootfs.tar.zst"
previous_sha256 = "80706af2261e0255c98eafe97c24d5e7970d821f87add64a2f0f5ba3c9410b65"

current_version = "latest02"
current_date = "20230315"
old_file = "oracle_amd64_2023-01-15_00-07-rootfs.tar.zst"
old_sha256 = "5ce3b8e131c04979e61d1bbb8f0470a6b413e0c09ddc91395bf74d0dcadbc631"
# edition 2021
# DISTRO_NAME=oracle_amd64
# ROOTFS_FILE=oracle_amd64_2023-03-15_00-06-rootfs.tar.zst
# SHA256SUM=3d8037dddf83aac07df7a30a0ae423548b23a8398c8d559a101a9437681722af
# BUILD_DATE=20230315
# BUILD_TAG=2023-03-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-15
begin = 2023-03-15 00:03:18.195691271+00:00
start-sync_0 = 00:04:26
start-zstd = 00:04:46
start-sync_1 = 00:06:14
end-sync_1 = 00:06:24
end = 2023-03-15 00:06:24.205428624+00:00

[server]
repo = "cake233/oracle-amd64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = true
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = true
previous = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```