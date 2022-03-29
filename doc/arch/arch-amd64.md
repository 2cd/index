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
tag = ["base", "2022-03-29"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "arch_amd64_2022-03-29_23-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "deb9323776b0add7cdd934828741c24a1c37971c9426ecc0013c4860aef320fb"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "624M"
tar_bytes = 653570560

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "182M"
zstd_bytes = 189810613

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220329"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch_amd64_2022-03-29_23-05-rootfs.tar.zst
# SHA256SUM=deb9323776b0add7cdd934828741c24a1c37971c9426ecc0013c4860aef320fb
# BUILD_DATE=20220329
# BUILD_TAG=2022-03-29
# STATUS=completed
# VERSION=latest01
# END_TIME=23:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-29
begin = 2022-03-29 23:02:25.031796017+00:00
start-sync_0 = 23:03:46
start-zstd = 23:04:37
start-sync_1 = 23:05:00
end-sync_1 = 23:05:19
end = 2022-03-29 23:05:19.025896539+00:00

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
