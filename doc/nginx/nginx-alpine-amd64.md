# nginx-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name nginx-alpine-amd64 \
    cake233/nginx-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it nginx-alpine-amd64 bash
```

## nginx-alpine-amd64.toml

```toml
[main]
name = "nginx"
tag = ["alpine", "2023-09-04", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_amd64_2023-09-04_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e03b724006afc278d7645fec5eba9007ab072a8288771e06bcf618a922f02c88"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "51M"
tar_bytes = 53293056

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "15M"
zstd_bytes = 15097275

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230904"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx-musl_amd64_2023-09-04_12-04-rootfs.tar.zst
# SHA256SUM=e03b724006afc278d7645fec5eba9007ab072a8288771e06bcf618a922f02c88
# BUILD_DATE=20230904
# BUILD_TAG=2023-09-04
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-04
begin = 2023-09-04 12:02:49.727950924+00:00
start-sync_0 = 12:04:02
start-zstd = 12:04:11
start-sync_1 = 12:04:43
end-sync_1 = 12:04:51
end = 2023-09-04 12:04:51.805413013+00:00

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (x86_64) Version 1.2.4'
nginx = '1.25.2'
njs = '0.8.0'
pkg_release = '1'
```