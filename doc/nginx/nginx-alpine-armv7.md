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
tag = ["alpine", "2022-09-05", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_armhf_2022-09-05_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fc8e9d87fa59e22750235066fd1f0370130e20cfa48b794ca08db62a36854e97"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "25M"
tar_bytes = 25411584

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "8.4M"
zstd_bytes = 8795726

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220822"
previous_tag = "2022-08-22"
previous_file = "nginx-musl_armhf_2022-08-22_12-03-rootfs.tar.zst"
previous_sha256 = "ac279a965245b331fe7b2bcdd84f9d652a04015ae09ea1090855c959e0b1daf3"

current_version = "latest02"
current_date = "20220905"
old_file = "nginx-musl_armhf_2022-08-08_12-03-rootfs.tar.zst"
old_sha256 = "61ed513cfff592480dc00466a70fdd6592af55d577913afeb1639f37565deecb"
# edition 2021
# DISTRO_NAME=nginx_armhf
# ROOTFS_FILE=nginx-musl_armhf_2022-09-05_12-04-rootfs.tar.zst
# SHA256SUM=fc8e9d87fa59e22750235066fd1f0370130e20cfa48b794ca08db62a36854e97
# BUILD_DATE=20220905
# BUILD_TAG=2022-09-05
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-05
begin = 2022-09-05 12:02:28.555961347+00:00
start-sync_0 = 12:03:31
start-zstd = 12:03:40
start-sync_1 = 12:03:51
end-sync_1 = 12:04:01
end = 2022-09-05 12:04:01.057307928+00:00

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
