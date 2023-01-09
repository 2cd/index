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
tag = ["latest", "2023-01-09"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx_amd64_2023-01-09_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7b10067668d7b08bca2c3dcc94c87d748738580a6733f3117456a458b8217cf2"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "163M"
tar_bytes = 170391040

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "40M"
zstd_bytes = 41602696

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221226"
previous_tag = "2022-12-26"
previous_file = "nginx_amd64_2022-12-26_12-04-rootfs.tar.zst"
previous_sha256 = "b15bda57216d41ab52d9c9de9909fc751b0f447b022818e0708efed7361c867e"

current_version = "latest01"
current_date = "20230109"
old_file = "nginx_amd64_2022-12-12_12-06-rootfs.tar.zst"
old_sha256 = "b5ac721f29c168c299c175dd6abca5b59cc818569a4c2529dffef01ff5feae91"
# edition 2021
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx_amd64_2023-01-09_12-05-rootfs.tar.zst
# SHA256SUM=7b10067668d7b08bca2c3dcc94c87d748738580a6733f3117456a458b8217cf2
# BUILD_DATE=20230109
# BUILD_TAG=2023-01-09
# STATUS=completed
# VERSION=latest01
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-09
begin = 2023-01-09 12:02:33.626303672+00:00
start-sync_0 = 12:03:26
start-zstd = 12:03:34
start-sync_1 = 12:05:00
end-sync_1 = 12:05:07
end = 2023-01-09 12:05:07.952958200+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
nginx = '1.23.3'
njs = '0.7.9'
pkg_release = '1~bullseye'
```
