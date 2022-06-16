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
tag = ["alpine", "2022-06-16", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_amd64_2022-06-16_06-39.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7fe1c665d2e96d646a768d391c78a9b3c44baab5e1e6f41dc4a123bf0b9c6b0e"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "35M"
tar_bytes = 36036608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "9.3M"
zstd_bytes = 9666798

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220613"
previous_tag = "2022-06-13"
previous_file = "nginx-musl_amd64_2022-06-13_12-03-rootfs.tar.zst"
previous_sha256 = "56af37b6f8182930c045acfc3a9f0905ee6d18c5c5699d07d2cbeefbf1e55878"

current_version = "latest02"
current_date = "20220616"
old_file = "nginx-musl_amd64_2022-05-30_12-03-rootfs.tar.zst"
old_sha256 = "c34c726f32cff3b7da1ac32386a76c7d15e0673093b65ada978a7df124ef0edb"
# edition 2021
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx-musl_amd64_2022-06-16_06-39-rootfs.tar.zst
# SHA256SUM=7fe1c665d2e96d646a768d391c78a9b3c44baab5e1e6f41dc4a123bf0b9c6b0e
# BUILD_DATE=20220616
# BUILD_TAG=2022-06-16
# STATUS=completed
# VERSION=latest02
# END_TIME=06:39

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-16
begin = 2022-06-16 06:38:28.662373737+00:00
start-sync_0 = 06:39:00
start-zstd = 06:39:13
start-sync_1 = 06:39:34
end-sync_1 = 06:39:45
end = 2022-06-16 06:39:45.733051332+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.2'
nginx = '1.21.6'
njs = '0.7.3'
pkg_release = '1'
```
