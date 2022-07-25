# nginx-alpine-armv7

## How to run it?

```sh
docker run \
    -it \
    --name nginx-alpine-armv7 \
    cake233/nginx-alpine-armv7
```

## How to exec shell?

```sh
docker exec -it nginx-alpine-armv7 bash
```

## nginx-alpine-armv7.toml

```toml
[main]
name = "nginx"
tag = ["alpine", "2022-07-25", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_armhf_2022-07-25_12-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ae1df49b2225d3280cb2620c91fcae8ab7cfacc464626ab013887757bf986095"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "25M"
tar_bytes = 25432576

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "8.4M"
zstd_bytes = 8787484

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220711"
previous_tag = "2022-07-11"
previous_file = "nginx-musl_armhf_2022-07-11_12-03-rootfs.tar.zst"
previous_sha256 = "94f63a985713586c3779e0c96e6ffce31bf6bca0934d895b5eb95b9afb2d159a"

current_version = "latest02"
current_date = "20220725"
old_file = "nginx-musl_armhf_2022-06-27_12-03-rootfs.tar.zst"
old_sha256 = "aa67d0dc7841d19d04ac71f6e9ec7763c28804fea81976661290666a048e4588"
# edition 2021
# DISTRO_NAME=nginx_armhf
# ROOTFS_FILE=nginx-musl_armhf_2022-07-25_12-03-rootfs.tar.zst
# SHA256SUM=ae1df49b2225d3280cb2620c91fcae8ab7cfacc464626ab013887757bf986095
# BUILD_DATE=20220725
# BUILD_TAG=2022-07-25
# STATUS=completed
# VERSION=latest02
# END_TIME=12:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-25
begin = 2022-07-25 12:02:40.583325002+00:00
start-sync_0 = 12:03:26
start-zstd = 12:03:37
start-sync_1 = 12:03:48
end-sync_1 = 12:03:57
end = 2022-07-25 12:03:57.775716496+00:00

[server]
repo = "cake233/nginx-alpine-armv7"

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
ldd = 'musl libc (armhf) Version 1.2.3'
nginx = '1.23.1'
njs = '0.7.6'
pkg_release = '1'
```
