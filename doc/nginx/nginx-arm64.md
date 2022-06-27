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
tag = ["latest", "2022-06-27"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx_arm64_2022-06-27_12-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b6a9aef936ca56d1d8e2ca189bf409f2eeafa85776da24513a3919bfa809bf74"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "156M"
tar_bytes = 162988032

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "39M"
zstd_bytes = 40647059

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220613"
previous_tag = "2022-06-13"
previous_file = "nginx_arm64_2022-06-13_12-06-rootfs.tar.zst"
previous_sha256 = "d4b828b993a823b3c106a6096ac84618055d90be9255bc7656d07e7bbd8aa7bb"

current_version = "latest02"
current_date = "20220627"
old_file = "nginx_arm64_2022-05-30_12-07-rootfs.tar.zst"
old_sha256 = "5b0a4ae49afa6d37d571032e1cfb536a937712617f8ead13b87b7b5253f76162"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx_arm64_2022-06-27_12-06-rootfs.tar.zst
# SHA256SUM=b6a9aef936ca56d1d8e2ca189bf409f2eeafa85776da24513a3919bfa809bf74
# BUILD_DATE=20220627
# BUILD_TAG=2022-06-27
# STATUS=completed
# VERSION=latest02
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-27
begin = 2022-06-27 12:02:33.808473504+00:00
start-sync_0 = 12:04:48
start-zstd = 12:04:58
start-sync_1 = 12:06:28
end-sync_1 = 12:06:36
end = 2022-06-27 12:06:36.720190723+00:00

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
nginx = '1.23.0'
njs = '0.7.5'
pkg_release = '1~bullseye'
```
