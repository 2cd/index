# nginx-amd64

## How to run it?

```sh
docker run \
    -it \
    --name nginx-amd64 \
    cake233/nginx-amd64
```

## How to exec shell?

```sh
docker exec -it nginx-amd64 bash
```

## nginx-amd64.toml

```toml
[main]
name = "nginx"
tag = ["latest", "2023-08-07"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx_amd64_2023-08-07_12-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ca4b5299857f804b200b330a5ac7c9435f501672ca0f9cea352e96467536ab57"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "207M"
tar_bytes = 216348672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "50M"
zstd_bytes = 51971968

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230724"
previous_tag = "2023-07-24"
previous_file = "nginx_amd64_2023-07-24_12-06-rootfs.tar.zst"
previous_sha256 = "c6466a5d302071527ecf3a645f573139774223a6d683a7d1c024e31d6d0ab5f5"

current_version = "latest01"
current_date = "20230807"
old_file = "nginx_amd64_2023-07-10_12-05-rootfs.tar.zst"
old_sha256 = "14ff7dbe0ab081ec485fe90f2efa8b9384a47eb702b2721c5d1e15634f5a5d93"
# edition 2021
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx_amd64_2023-08-07_12-06-rootfs.tar.zst
# SHA256SUM=ca4b5299857f804b200b330a5ac7c9435f501672ca0f9cea352e96467536ab57
# BUILD_DATE=20230807
# BUILD_TAG=2023-08-07
# STATUS=completed
# VERSION=latest01
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-07
begin = 2023-08-07 12:02:42.782818109+00:00
start-sync_0 = 12:04:07
start-zstd = 12:04:19
start-sync_1 = 12:06:20
end-sync_1 = 12:06:31
end = 2023-08-07 12:06:31.806674689+00:00

[server]
repo = "cake233/nginx-amd64"

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

[version]
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u1) 2.36'
nginx = '1.25.1'
njs = '0.7.12'
pkg_release = '1~bookworm'
```
