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
tag = ["base", "2022-01-05"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "arch_arm64_2022-01-05_00-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "3b104134de779e34d443dab076e3929d12ec009a7536de43b3baab45e70d87f4"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "643M"
tar_bytes = 673940480

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "177M"
zstd_bytes = 185518287

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220105"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch_arm64_2022-01-05_00-05-rootfs.tar.zst
# SHA256SUM=3b104134de779e34d443dab076e3929d12ec009a7536de43b3baab45e70d87f4
# BUILD_DATE=20220105
# BUILD_TAG=2022-01-05
# STATUS=completed
# VERSION=latest01
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-05
begin = 2022-01-05 00:02:26.616388712+00:00
start-sync_0 = 00:03:52
start-zstd = 00:04:38
start-sync_1 = 00:04:50
end-sync_1 = 00:05:09
end = 2022-01-05 00:05:09.603319781+00:00

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
