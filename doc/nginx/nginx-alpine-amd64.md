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
tag = ["alpine", "2022-03-01", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "nginx-musl_amd64_2022-03-01_19-00.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "c0ab2678cbb60a2f95097835a6fb2145980a619c6059f98aeb1a00fb8cd407d2"

# zstd: [1-22]
zstd-level = 11

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "35M"
tar_bytes = 36025344

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "11M"
zstd_bytes = 11513368

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220207"
previous_tag = "2022-02-07"
previous_file = "nginx-musl_amd64_2022-02-07_12-03-rootfs.tar.zst"
previous_sha256 = "5a177f068dc9e9c36c29cb05f95d78a3e2c64e8ac8168d6186c266c56e3486fa"

current_version = "latest01"
current_date = "20220301"
old_file = "nginx-musl_amd64_2022-01-24_12-03-rootfs.tar.zst"
old_sha256 = "683341f75a31f8c22b31e9dd37d2ede1033ca87040bf3879d4bbc29c864de310"
# edition 2021
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx-musl_amd64_2022-03-01_19-00-rootfs.tar.zst
# SHA256SUM=c0ab2678cbb60a2f95097835a6fb2145980a619c6059f98aeb1a00fb8cd407d2
# BUILD_DATE=20220301
# BUILD_TAG=2022-03-01
# STATUS=completed
# VERSION=latest01
# END_TIME=19:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-01
begin = 2022-03-01 19:00:34.065106078+00:00
start-sync_0 = 19:00:44
start-zstd = 19:00:50
start-sync_1 = 19:00:51
end-sync_1 = 19:00:56
end = 2022-03-01 19:00:56.310057939+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.2'
nginx = '1.21.6'
njs = '0.7.2'
pkg_release = '1'
```
