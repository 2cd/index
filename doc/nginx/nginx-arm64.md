# nginx-arm64

## How to run it?

```sh
docker run \
    -it \
    --name nginx-arm64 \
    cake233/nginx-arm64
```

## How to exec shell?

```sh
docker exec -it nginx-arm64 bash
```

## nginx-arm64.toml

```toml
[main]
name = "nginx"
tag = ["latest", "2023-12-25"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx_arm64_2023-12-25_12-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8c0d1a73e3b203dbcddec047583850e8be9097179c7273e1190a91b603b645ac"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "213M"
tar_bytes = 223246336

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "47M"
zstd_bytes = 48722211

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231127"
previous_tag = "2023-11-27"
previous_file = "nginx_arm64_2023-11-27_12-06-rootfs.tar.zst"
previous_sha256 = "5123d699946c7f058a9c46dc0ec230328fd2311675057783f5102fde48c9df42"

current_version = "latest01"
current_date = "20231225"
old_file = "nginx_arm64_2023-11-13_12-06-rootfs.tar.zst"
old_sha256 = "3f9b95137b93102e323a1780656fbfc37a52585ccc59452fd7003e5033f2cd0d"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx_arm64_2023-12-25_12-07-rootfs.tar.zst
# SHA256SUM=8c0d1a73e3b203dbcddec047583850e8be9097179c7273e1190a91b603b645ac
# BUILD_DATE=20231225
# BUILD_TAG=2023-12-25
# STATUS=completed
# VERSION=latest01
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-25
begin = 2023-12-25 12:02:38.653768372+00:00
start-sync_0 = 12:05:05
start-zstd = 12:05:19
start-sync_1 = 12:06:52
end-sync_1 = 12:07:03
end = 2023-12-25 12:07:03.979827335+00:00

[server]
repo = "cake233/nginx-arm64"

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
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u3) 2.36'
nginx = '1.25.3'
njs = '0.8.2'
pkg_release = '1~bookworm'
```
