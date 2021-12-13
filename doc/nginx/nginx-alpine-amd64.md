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
tag = ["alpine", "2021-12-13", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "nginx-musl_amd64_2021-12-13_12-03.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "114e89bde9ed8fe1dd52415b2b4518dc46bd8d7c8fef195c22385b5bec17d935"

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
zstd_bytes = 9434859

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211208"
previous_tag = "2021-12-08"
previous_file = "nginx-musl_amd64_2021-12-08_01-07-rootfs.tar.zst"
previous_sha256 = "b862e2aa18d6703294973ec07a25c45609ad0c4eee1017b10250c073fdae49ed"

current_version = "latest01"
current_date = "20211213"
old_file = "nginx-musl_amd64_2021-11-28_23-00-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx-musl_amd64_2021-12-13_12-03-rootfs.tar.zst
# SHA256SUM=114e89bde9ed8fe1dd52415b2b4518dc46bd8d7c8fef195c22385b5bec17d935
# BUILD_DATE=20211213
# BUILD_TAG=2021-12-13
# STATUS=completed
# VERSION=latest01
# END_TIME=12:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-13
begin = 2021-12-13 12:02:29.950667461+00:00
start-sync_0 = 12:03:15
start-zstd = 12:03:24
start-sync_1 = 12:03:39
end-sync_1 = 12:03:46
end = 2021-12-13 12:03:46.958051560+00:00

[server]
repo = "cake233/nginx-alpine-amd64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
previous = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "C.UTF-8"

[version]
ldd = ''
nginx = '1.21.4'
njs = '0.7.0'
pkg_release = '1'
```
