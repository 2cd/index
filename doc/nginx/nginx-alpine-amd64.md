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
tag = ["alpine", "2022-07-11", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_amd64_2022-07-11_12-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f913326abfa2cdd0a4da85712682adf8b1108cfaa4dc9658c5bc0bbf5a70d212"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "35M"
tar_bytes = 35990016

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "9.3M"
zstd_bytes = 9712120

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220627"
previous_tag = "2022-06-27"
previous_file = "nginx-musl_amd64_2022-06-27_12-04-rootfs.tar.zst"
previous_sha256 = "dac915b3c63cb50865aff2a61684f151a64f52f40a9d2c52494bc205b53c5b25"

current_version = "latest01"
current_date = "20220711"
old_file = "nginx-musl_amd64_2022-06-13_12-03-rootfs.tar.zst"
old_sha256 = "56af37b6f8182930c045acfc3a9f0905ee6d18c5c5699d07d2cbeefbf1e55878"
# edition 2021
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx-musl_amd64_2022-07-11_12-03-rootfs.tar.zst
# SHA256SUM=f913326abfa2cdd0a4da85712682adf8b1108cfaa4dc9658c5bc0bbf5a70d212
# BUILD_DATE=20220711
# BUILD_TAG=2022-07-11
# STATUS=completed
# VERSION=latest01
# END_TIME=12:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-11
begin = 2022-07-11 12:02:29.963995304+00:00
start-sync_0 = 12:02:55
start-zstd = 12:03:02
start-sync_1 = 12:03:18
end-sync_1 = 12:03:22
end = 2022-07-11 12:03:22.951346147+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.3'
nginx = '1.23.0'
njs = '0.7.5'
pkg_release = '1'
```
