# nginx-alpine-armv7

## How to run it?

```shell
docker run \
    -it \
    --name nginx-alpine-armv7 \
    cake233/nginx-alpine-armv7
```

## How to exec shell?

```shell
    docker exec -it nginx-alpine-armv7 bash
```

## nginx-alpine-armv7.toml

```toml
[main]
name = "nginx"
tag = ["alpine", "2021-11-28", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "nginx-musl_armhf_2021-11-28_23-01.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "46e93a7ced29341468cf820f2c2219438b299f7165c3d8ba99fee24b0e675a11"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "24M"
tar_bytes = 24918016

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "8.2M"
zstd_bytes = 8541250

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211128"
last_tag = ""
last_file = ""

current_version = "latest01"
current_date = "20211128"
# edition 2021
# DISTRO_NAME=nginx_armhf
# ROOTFS_FILE=nginx-musl_armhf_2021-11-28_23-01.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest01
# END_TIME=23:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 23:00:23.148488917+00:00
start-sync_0 = 23:00:44
start-zstd = 23:00:51
start-sync_1 = 23:00:59
end-sync_1 = 23:01:05
end = 2021-11-28 23:01:05.243673355+00:00

[server]
repo = "cake233/nginx-alpine-armv7"

[server.node1]
name = "cn"
current = false
last = true
split = false

[server.node2]
name = "us"
current = false
last = true
split = false
part = 12

[server.node3]
name = "global"
current = false
last = true
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "C.UTF-8"

[version]
nginx = '1.21.4'
njs = '0.7.0'
pkg_release = '1'
```
