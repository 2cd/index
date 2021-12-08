# arch-amd64

## How to run it?

```shell
docker run \
    -it \
    --name arch-amd64 \
    cake233/arch-amd64
```

## How to exec shell?

```shell
    docker exec -it arch-amd64 sh
```

## arch-amd64.toml

```toml
[main]
name = "arch"
tag = ["base", "2021-12-08"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "arch_amd64_2021-12-08_01-09.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "f974408be19cf25ad9a9bfbbcb095981ae28f1f1d292cb8f8e64945f8d7e6d14"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "622M"
tar_bytes = 651304448

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "178M"
zstd_bytes = 186607534

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211128"
last_tag = ""
last_file = ""
last_sha256 = ""

current_version = "latest01"
current_date = "20211208"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch_amd64_2021-12-08_01-09-rootfs.tar.zst
# SHA256SUM=f974408be19cf25ad9a9bfbbcb095981ae28f1f1d292cb8f8e64945f8d7e6d14
# BUILD_DATE=20211208
# BUILD_TAG=2021-12-08
# STATUS=completed
# VERSION=latest01
# END_TIME=01:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-08
begin = 2021-12-08 01:07:15.349836265+00:00
start-sync_0 = 01:08:17
start-zstd = 01:09:03
start-sync_1 = 01:09:16
end-sync_1 = 01:09:38
end = 2021-12-08 01:09:38.476196848+00:00

[server]
repo = "cake233/arch-amd64"

[server.node1]
name = "cn"
current = false
last = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
last = false
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
last = false
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
