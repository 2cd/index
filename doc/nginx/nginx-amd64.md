# nginx-amd64

## How to run it?

```sh
docker run \
    -it \
    --name nginx-amd64 \
    cake233/nginx-amd64
```

## How to exec shell?

```sh
docker exec -it nginx-amd64 bash
```

## nginx-amd64.toml

```toml
[main]
name = "nginx"
tag = ["latest", "2022-07-11"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx_amd64_2022-07-11_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "07ac3ebcf725a2fe260893e2b50aecbed77fe3e050e4e517105c3f90d82d77b2"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "163M"
tar_bytes = 170101248

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "40M"
zstd_bytes = 41563606

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220627"
previous_tag = "2022-06-27"
previous_file = "nginx_amd64_2022-06-27_12-05-rootfs.tar.zst"
previous_sha256 = "94f1bd1cc42528a4726189dbd1c45bb54bb4788a3e7f7d293891aba639849bb7"

current_version = "latest01"
current_date = "20220711"
old_file = "nginx_amd64_2022-06-13_12-05-rootfs.tar.zst"
old_sha256 = "f2b0e2141c0d939d98f7e8760aae9b8bcc50be465bd9e324fffeddbbfff9c094"
# edition 2021
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx_amd64_2022-07-11_12-05-rootfs.tar.zst
# SHA256SUM=07ac3ebcf725a2fe260893e2b50aecbed77fe3e050e4e517105c3f90d82d77b2
# BUILD_DATE=20220711
# BUILD_TAG=2022-07-11
# STATUS=completed
# VERSION=latest01
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-11
begin = 2022-07-11 12:02:33.540469865+00:00
start-sync_0 = 12:03:14
start-zstd = 12:03:29
start-sync_1 = 12:05:02
end-sync_1 = 12:05:13
end = 2022-07-11 12:05:13.134184520+00:00

[server]
repo = "cake233/nginx-amd64"

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
nginx = '1.23.0'
njs = '0.7.5'
pkg_release = '1~bullseye'
```
