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
tag = ["base", "2022-04-13"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "arch_arm64_2022-04-13_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9946eae04a1594bbcdd3efb1ffe2f7ddb19b2f52925d82bb26ee222d47a436e7"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "624M"
tar_bytes = 653596672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "179M"
zstd_bytes = 187512747

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220413"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch_arm64_2022-04-13_00-05-rootfs.tar.zst
# SHA256SUM=9946eae04a1594bbcdd3efb1ffe2f7ddb19b2f52925d82bb26ee222d47a436e7
# BUILD_DATE=20220413
# BUILD_TAG=2022-04-13
# STATUS=completed
# VERSION=latest01
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-13
begin = 2022-04-13 00:02:53.213055518+00:00
start-sync_0 = 00:04:15
start-zstd = 00:05:05
start-sync_1 = 00:05:26
end-sync_1 = 00:05:46
end = 2022-04-13 00:05:46.723963415+00:00

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
