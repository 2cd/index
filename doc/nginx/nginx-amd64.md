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
tag = ["latest", "2023-12-25"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx_amd64_2023-12-25_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a4ed17a4a902be10baa26f857472bcb0e05f4ad98387679f784a82ee1ab82070"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "207M"
tar_bytes = 216210944

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "50M"
zstd_bytes = 51958934

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231127"
previous_tag = "2023-11-27"
previous_file = "nginx_amd64_2023-11-27_12-06-rootfs.tar.zst"
previous_sha256 = "c5416b0323a5e9d6bea0f5f3d918aa1da58e8383802d489173d7891f7c1ff0e9"

current_version = "latest02"
current_date = "20231225"
old_file = "nginx_amd64_2023-11-13_12-06-rootfs.tar.zst"
old_sha256 = "9ac9471c16c46a3d83206e0ac58a6de5b4be85d779bb1f2644096586e18b3814"
# edition 2021
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx_amd64_2023-12-25_12-05-rootfs.tar.zst
# SHA256SUM=a4ed17a4a902be10baa26f857472bcb0e05f4ad98387679f784a82ee1ab82070
# BUILD_DATE=20231225
# BUILD_TAG=2023-12-25
# STATUS=completed
# VERSION=latest02
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-25
begin = 2023-12-25 12:02:36.905150919+00:00
start-sync_0 = 12:03:46
start-zstd = 12:03:59
start-sync_1 = 12:05:42
end-sync_1 = 12:05:54
end = 2023-12-25 12:05:54.337578695+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u3) 2.36'
nginx = '1.25.3'
njs = '0.8.2'
pkg_release = '1~bookworm'
```
