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
tag = ["base", "2022-02-09"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "arch_amd64_2022-02-09_00-04.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "11133e8cd0db390a43cea68c5a7c547e9232da7d2c900a5afb2610a666445735"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "618M"
tar_bytes = 647699968

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "179M"
zstd_bytes = 187604603

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220209"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch_amd64_2022-02-09_00-04-rootfs.tar.zst
# SHA256SUM=11133e8cd0db390a43cea68c5a7c547e9232da7d2c900a5afb2610a666445735
# BUILD_DATE=20220209
# BUILD_TAG=2022-02-09
# STATUS=completed
# VERSION=latest01
# END_TIME=00:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-09
begin = 2022-02-09 00:02:32.882488115+00:00
start-sync_0 = 00:03:38
start-zstd = 00:04:19
start-sync_1 = 00:04:34
end-sync_1 = 00:04:50
end = 2022-02-09 00:04:50.748429349+00:00

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
current = false
previous = false
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
