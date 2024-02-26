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
tag = ["alpine", "2024-02-26", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_amd64_2024-02-26_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d36cfd8c2a3638dcae6a8fc4ad2ca973821393b371e5a2e292ca0b090a148fb6"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "51M"
tar_bytes = 53312000

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "15M"
zstd_bytes = 15125303

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231127"
previous_tag = "2023-11-27"
previous_file = "nginx-musl_amd64_2023-11-27_12-04-rootfs.tar.zst"
previous_sha256 = "5e9ec766a71ee4e7b318514e47d362706cdffb1d942773847a4690edb4b2865e"

current_version = "latest02"
current_date = "20240226"
old_file = "nginx-musl_amd64_2023-10-16_12-04-rootfs.tar.zst"
old_sha256 = "58dfde817c2d6ed981353798e6fb3690eefa49ceedc1f0d2f24329714f504671"
# edition 2021
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx-musl_amd64_2024-02-26_12-04-rootfs.tar.zst
# SHA256SUM=d36cfd8c2a3638dcae6a8fc4ad2ca973821393b371e5a2e292ca0b090a148fb6
# BUILD_DATE=20240226
# BUILD_TAG=2024-02-26
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-26
begin = 2024-02-26 12:02:34.842554534+00:00
start-sync_0 = 12:03:58
start-zstd = 12:04:06
start-sync_1 = 12:04:31
end-sync_1 = 12:04:37
end = 2024-02-26 12:04:37.497828562+00:00

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
nginx = '1.25.4'
njs = '0.8.3'
pkg_release = '1'
```
