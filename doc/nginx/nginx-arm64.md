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
tag = ["latest", "2023-04-03"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx_arm64_2023-04-03_12-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f9c9cde25ea4bc645a33c939cc19f1932cd2461e64db762aaa4ef6c93d403e4b"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "156M"
tar_bytes = 163457536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "39M"
zstd_bytes = 40629587

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230320"
previous_tag = "2023-03-20"
previous_file = "nginx_arm64_2023-03-20_12-07-rootfs.tar.zst"
previous_sha256 = "5c34e08092f2bb2781a57523294942cb8118372d569f389546dac725b8a56df3"

current_version = "latest01"
current_date = "20230403"
old_file = "nginx_arm64_2023-03-06_12-06-rootfs.tar.zst"
old_sha256 = "4cad6c88fd3596112e0cbd73bcccf1ca6402ac96a80feae431371775e32dba59"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx_arm64_2023-04-03_12-07-rootfs.tar.zst
# SHA256SUM=f9c9cde25ea4bc645a33c939cc19f1932cd2461e64db762aaa4ef6c93d403e4b
# BUILD_DATE=20230403
# BUILD_TAG=2023-04-03
# STATUS=completed
# VERSION=latest01
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-03
begin = 2023-04-03 12:02:41.855565502+00:00
start-sync_0 = 12:05:21
start-zstd = 12:05:34
start-sync_1 = 12:07:23
end-sync_1 = 12:07:33
end = 2023-04-03 12:07:33.079996294+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
nginx = '1.23.4'
njs = '0.7.11'
pkg_release = '1~bullseye'
```
