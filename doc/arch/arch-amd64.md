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
tag = ["base", "2022-05-01"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch_amd64_2022-05-01_19-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7237a1f1fc691c895faf4568979a6bb0abf272e678e43b34f2bec3bb9467ae33"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "861M"
tar_bytes = 902118912

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "251M"
zstd_bytes = 262582812

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220501"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch_amd64_2022-05-01_19-29-rootfs.tar.zst
# SHA256SUM=7237a1f1fc691c895faf4568979a6bb0abf272e678e43b34f2bec3bb9467ae33
# BUILD_DATE=20220501
# BUILD_TAG=2022-05-01
# STATUS=completed
# VERSION=latest01
# END_TIME=19:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-01
begin = 2022-05-01 19:26:40.106852198+00:00
start-sync_0 = 19:27:50
start-zstd = 19:28:32
start-sync_1 = 19:28:55
end-sync_1 = 19:29:16
end = 2022-05-01 19:29:16.246096982+00:00

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
