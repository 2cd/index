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
tag = ["alpine", "2022-02-07", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "nginx-musl_arm64_2022-02-07_12-03.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "1539df8d4eff6948273a0787099d14fcc9da953b249564f29351bb8a808591d5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "33M"
tar_bytes = 34188288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "9.0M"
zstd_bytes = 9412207

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220124"
previous_tag = "2022-01-24"
previous_file = "nginx-musl_arm64_2022-01-24_12-03-rootfs.tar.zst"
previous_sha256 = "8faf6095a396f3a8dc60157d73870da25f462b97466aaf27e12a1936f0c306fd"

current_version = "latest02"
current_date = "20220207"
old_file = "nginx-musl_arm64_2021-12-27_12-03-rootfs.tar.zst"
old_sha256 = "803de12b6b48be62f4f2fd8a848027a8249b8f877ec19aae35e22a997cdf6782"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx-musl_arm64_2022-02-07_12-03-rootfs.tar.zst
# SHA256SUM=1539df8d4eff6948273a0787099d14fcc9da953b249564f29351bb8a808591d5
# BUILD_DATE=20220207
# BUILD_TAG=2022-02-07
# STATUS=completed
# VERSION=latest02
# END_TIME=12:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-07
begin = 2022-02-07 12:02:38.933333238+00:00
start-sync_0 = 12:03:28
start-zstd = 12:03:37
start-sync_1 = 12:03:51
end-sync_1 = 12:03:58
end = 2022-02-07 12:03:58.919419473+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.2'
nginx = '1.21.6'
njs = '0.7.2'
pkg_release = '1'
```
