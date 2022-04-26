# euler-amd64

## How to run it?

```sh
docker run \
    -it \
    --name euler-amd64 \
    cake233/euler-amd64
```

## How to exec shell?

```sh
docker exec -it euler-amd64 sh
```

## euler-amd64.toml

```toml
[main]
name = "euler"
tag = ["base", "2022-04-26"]
os = "euler"
release = "base"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "euler_amd64_2022-04-26_02-42.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "102de50eab90c320532dc4c2c88d962cb271511d7808575dcc1a13c5f7c99e4f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "445M"
tar_bytes = 466259968

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "70M"
zstd_bytes = 72536551

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220422"
previous_tag = "2022-04-22"
previous_file = "euler_amd64_2022-04-22_00-50-rootfs.tar.zst"
previous_sha256 = "377a436edc19dea57b0f4852ebf3026c49b348489f789cda46f27de68b78c85b"

current_version = "latest02"
current_date = "20220426"
old_file = "euler_amd64_2022-04-22_09-51-rootfs.tar.zst"
old_sha256 = "ca47af1ef86244f5d4f279d8e3636b4c868fb6b35474c6d2ac5cc19173356d76"
# edition 2021
# DISTRO_NAME=euler_amd64
# ROOTFS_FILE=euler_amd64_2022-04-26_02-42-rootfs.tar.zst
# SHA256SUM=102de50eab90c320532dc4c2c88d962cb271511d7808575dcc1a13c5f7c99e4f
# BUILD_DATE=20220426
# BUILD_TAG=2022-04-26
# STATUS=completed
# VERSION=latest02
# END_TIME=02:42

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-26
begin = 2022-04-26 02:37:54.877192387+00:00
start-sync_0 = 02:40:15
start-zstd = 02:40:38
start-sync_1 = 02:42:08
end-sync_1 = 02:42:17
end = 2022-04-26 02:42:17.935309479+00:00

[server]
repo = "cake233/euler-amd64"

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
