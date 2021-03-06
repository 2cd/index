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
tag = ["base", "2022-06-15"]
os = "euler"
release = "base"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "euler_amd64_2022-06-15_00-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5c747ec0fad1fe57a75aa8119af8ebd602ec434ec6863aa4f3037873c41b2e7b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "450M"
tar_bytes = 471696896

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "70M"
zstd_bytes = 72927826

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220515"
previous_tag = "2022-05-15"
previous_file = "euler_amd64_2022-05-15_00-07-rootfs.tar.zst"
previous_sha256 = "4278815a65b9a1329b635640e5a8dd378b66434a433d1e7082cd917b739d836b"

current_version = "latest01"
current_date = "20220615"
old_file = "euler_amd64_2022-04-22_00-50-rootfs.tar.zst"
old_sha256 = "377a436edc19dea57b0f4852ebf3026c49b348489f789cda46f27de68b78c85b"
# edition 2021
# DISTRO_NAME=euler_amd64
# ROOTFS_FILE=euler_amd64_2022-06-15_00-07-rootfs.tar.zst
# SHA256SUM=5c747ec0fad1fe57a75aa8119af8ebd602ec434ec6863aa4f3037873c41b2e7b
# BUILD_DATE=20220615
# BUILD_TAG=2022-06-15
# STATUS=completed
# VERSION=latest01
# END_TIME=00:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-15
begin = 2022-06-15 00:03:58.649325645+00:00
start-sync_0 = 00:05:57
start-zstd = 00:06:17
start-sync_1 = 00:07:35
end-sync_1 = 00:07:45
end = 2022-06-15 00:07:45.216965026+00:00

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
