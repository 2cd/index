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
tag = ["alpine", "2022-05-15", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_arm64_2022-05-15_15-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1aab8af909e5043fd526bf57c3497984eabc31479b483f628b1eb36eb792c535"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "33M"
tar_bytes = 34192384

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "9.0M"
zstd_bytes = 9403631

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220502"
previous_tag = "2022-05-02"
previous_file = "nginx-musl_arm64_2022-05-02_12-03-rootfs.tar.zst"
previous_sha256 = "4ee936846534adfb97a3ec95623f296cc4bce5a2b308a66ad06ff2a02e215bee"

current_version = "latest01"
current_date = "20220515"
old_file = "nginx-musl_arm64_2022-04-18_12-04-rootfs.tar.zst"
old_sha256 = "d8862d6519f6989929b8ab4c1228b305778d80edac168f60a673520a285e425d"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx-musl_arm64_2022-05-15_15-03-rootfs.tar.zst
# SHA256SUM=1aab8af909e5043fd526bf57c3497984eabc31479b483f628b1eb36eb792c535
# BUILD_DATE=20220515
# BUILD_TAG=2022-05-15
# STATUS=completed
# VERSION=latest01
# END_TIME=15:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-15
begin = 2022-05-15 15:02:37.069752271+00:00
start-sync_0 = 15:03:26
start-zstd = 15:03:31
start-sync_1 = 15:03:48
end-sync_1 = 15:03:52
end = 2022-05-15 15:03:52.925911184+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.2'
nginx = '1.21.6'
njs = '0.7.2'
pkg_release = '1'
```
