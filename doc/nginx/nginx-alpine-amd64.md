# nginx-alpine-amd64

## How to run it?

```shell
docker run \
    -it \
    --name nginx-alpine-amd64 \
    cake233/nginx-alpine-amd64
```

## How to exec shell?

```shell
    docker exec -it nginx-alpine-amd64 bash
```

## nginx-alpine-amd64.toml

```toml
[main]
name = "nginx"
tag = ["alpine", "2021-11-28", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "nginx-musl_amd64_2021-11-28_22-36.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "f6c28f53f1343ec587af4f7f3fd48c9dcc305d08a5761c99b68592660d3a1163"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "34M"
tar_bytes = 35259392

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "9.0M"
zstd_bytes = 9431283

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
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx-musl_amd64_2021-11-28_22-36.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest01
# END_TIME=22:36

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 22:35:34.817735837+00:00
start-sync_0 = 22:35:46
start-zstd = 22:35:51
start-sync_1 = 22:36:02
end-sync_1 = 22:36:07
end = 2021-11-28 22:36:07.204953648+00:00

[server]
repo = "cake233/nginx-alpine-amd64"

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
