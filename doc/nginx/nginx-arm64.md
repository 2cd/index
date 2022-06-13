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
tag = ["latest", "2022-06-13"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx_arm64_2022-06-13_12-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d4b828b993a823b3c106a6096ac84618055d90be9255bc7656d07e7bbd8aa7bb"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "156M"
tar_bytes = 162982912

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "39M"
zstd_bytes = 40576206

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220530"
previous_tag = "2022-05-30"
previous_file = "nginx_arm64_2022-05-30_12-07-rootfs.tar.zst"
previous_sha256 = "5b0a4ae49afa6d37d571032e1cfb536a937712617f8ead13b87b7b5253f76162"

current_version = "latest01"
current_date = "20220613"
old_file = "nginx_arm64_2022-05-16_12-06-rootfs.tar.zst"
old_sha256 = "c856c88ad27f14ca55ddfd0bf194534bd6963e4e5799b907dc4572c91150830f"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx_arm64_2022-06-13_12-06-rootfs.tar.zst
# SHA256SUM=d4b828b993a823b3c106a6096ac84618055d90be9255bc7656d07e7bbd8aa7bb
# BUILD_DATE=20220613
# BUILD_TAG=2022-06-13
# STATUS=completed
# VERSION=latest01
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-13
begin = 2022-06-13 12:02:38.639871960+00:00
start-sync_0 = 12:05:00
start-zstd = 12:05:14
start-sync_1 = 12:06:42
end-sync_1 = 12:06:54
end = 2022-06-13 12:06:54.263346108+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
nginx = '1.21.6'
njs = '0.7.3'
pkg_release = '1~bullseye'
```
