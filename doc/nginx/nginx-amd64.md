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
tag = ["latest", "2022-10-03"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx_amd64_2022-10-03_12-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "065163d314f290c6eb8c326fbf88ae5e6072d37e9711c55e3ad60c88643ea4e8"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "163M"
tar_bytes = 170236928

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "40M"
zstd_bytes = 41534408

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220919"
previous_tag = "2022-09-19"
previous_file = "nginx_amd64_2022-09-19_12-05-rootfs.tar.zst"
previous_sha256 = "7a177b132fb4feadcebf28ac714ab3f76dbfc620dfe2f7d72ac95ff4c385e028"

current_version = "latest02"
current_date = "20221003"
old_file = "nginx_amd64_2022-09-05_12-05-rootfs.tar.zst"
old_sha256 = "da71459490b8daeb0e7787de2c07cdc9cf7e9f1a1d53059cf408995b4adde8e0"
# edition 2021
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx_amd64_2022-10-03_12-06-rootfs.tar.zst
# SHA256SUM=065163d314f290c6eb8c326fbf88ae5e6072d37e9711c55e3ad60c88643ea4e8
# BUILD_DATE=20221003
# BUILD_TAG=2022-10-03
# STATUS=completed
# VERSION=latest02
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-03
begin = 2022-10-03 12:02:29.246575209+00:00
start-sync_0 = 12:03:40
start-zstd = 12:03:53
start-sync_1 = 12:05:52
end-sync_1 = 12:06:02
end = 2022-10-03 12:06:02.062815318+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u4) 2.31'
nginx = '1.23.1'
njs = '0.7.6'
pkg_release = '1~bullseye'
```
