# nginx-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name nginx-alpine-arm64 \
    cake233/nginx-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it nginx-alpine-arm64 bash
```

## nginx-alpine-arm64.toml

```toml
[main]
name = "nginx"
tag = ["alpine", "2022-07-11", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_arm64_2022-07-11_12-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c16418ed771e2a903d02a2da77cadc0d46686b61135f22f93dcaa3c4c9633d79"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "33M"
tar_bytes = 34224640

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "9.1M"
zstd_bytes = 9443748

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220627"
previous_tag = "2022-06-27"
previous_file = "nginx-musl_arm64_2022-06-27_12-03-rootfs.tar.zst"
previous_sha256 = "059378d4d6eef15ca4d60937291ad0eeab46cc5d2563986b45335b7161971991"

current_version = "latest01"
current_date = "20220711"
old_file = "nginx-musl_arm64_2022-06-13_12-04-rootfs.tar.zst"
old_sha256 = "7a20ea88d8f635057e7f165277076696647c1a9afe4ad7e90487f90a8faa5d75"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx-musl_arm64_2022-07-11_12-03-rootfs.tar.zst
# SHA256SUM=c16418ed771e2a903d02a2da77cadc0d46686b61135f22f93dcaa3c4c9633d79
# BUILD_DATE=20220711
# BUILD_TAG=2022-07-11
# STATUS=completed
# VERSION=latest01
# END_TIME=12:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-11
begin = 2022-07-11 12:02:29.902821954+00:00
start-sync_0 = 12:03:01
start-zstd = 12:03:07
start-sync_1 = 12:03:25
end-sync_1 = 12:03:31
end = 2022-07-11 12:03:31.344803727+00:00

[server]
repo = "cake233/nginx-alpine-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.3'
nginx = '1.23.0'
njs = '0.7.5'
pkg_release = '1'
```
