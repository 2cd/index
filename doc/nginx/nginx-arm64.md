# nginx-arm64

## How to run it?

```sh
docker run \
    -it \
    --name nginx-arm64 \
    cake233/nginx-arm64
```

## How to exec shell?

```sh
docker exec -it nginx-arm64 bash
```

## nginx-arm64.toml

```toml
[main]
name = "nginx"
tag = ["latest", "2023-09-18"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx_arm64_2023-09-18_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f56cef99fdf125baf2fdff4859393cacab60572bf69f226c0710830428ea2018"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "213M"
tar_bytes = 223286784

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "47M"
zstd_bytes = 48713177

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230904"
previous_tag = "2023-09-04"
previous_file = "nginx_arm64_2023-09-04_12-08-rootfs.tar.zst"
previous_sha256 = "abdf8ccae7baa2a652a560089363ffdad7655112d541b7b2fe6684c7dae8cecd"

current_version = "latest02"
current_date = "20230918"
old_file = "nginx_arm64_2023-08-21_12-07-rootfs.tar.zst"
old_sha256 = "8a3b5630eeebbd38db3505a8b57d11bd7a5e8dd25662f1e9ec33608efeb92b47"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx_arm64_2023-09-18_12-08-rootfs.tar.zst
# SHA256SUM=f56cef99fdf125baf2fdff4859393cacab60572bf69f226c0710830428ea2018
# BUILD_DATE=20230918
# BUILD_TAG=2023-09-18
# STATUS=completed
# VERSION=latest02
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-18
begin = 2023-09-18 12:02:43.315895168+00:00
start-sync_0 = 12:05:37
start-zstd = 12:05:54
start-sync_1 = 12:07:49
end-sync_1 = 12:08:01
end = 2023-09-18 12:08:01.580447146+00:00

[server]
repo = "cake233/nginx-arm64"

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
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u1) 2.36'
nginx = '1.25.2'
njs = '0.8.0'
pkg_release = '1~bookworm'
```
