# node-arm64

## How to run it?

```sh
docker run \
    -it \
    --name node-arm64 \
    cake233/node-arm64
```

## How to exec shell?

```sh
docker exec -it node-arm64 bash
```

## node-arm64.toml

```toml
[main]
name = "node"
tag = ["latest", "2022-06-20"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_arm64_2022-06-20_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8c572bc5c3059ea0e0e9c77b0ba664322e2d2160e7ec8aaa0558ab50b1423b71"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "951M"
tar_bytes = 996870144

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "198M"
zstd_bytes = 206595272

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220606"
previous_tag = "2022-06-06"
previous_file = "node_arm64_2022-06-06_12-11-rootfs.tar.zst"
previous_sha256 = "49390eb9fc32ee89007e05166b0381e8c4947c5daf61ea32fef32e49154c0ef1"

current_version = "latest02"
current_date = "20220620"
old_file = "node_arm64_2022-05-23_12-11-rootfs.tar.zst"
old_sha256 = "6e5c35660e0daed4c132d0956b8bb121fbe4e531af1dc1019edff3998dbd9a9d"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node_arm64_2022-06-20_12-10-rootfs.tar.zst
# SHA256SUM=8c572bc5c3059ea0e0e9c77b0ba664322e2d2160e7ec8aaa0558ab50b1423b71
# BUILD_DATE=20220620
# BUILD_TAG=2022-06-20
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-20
begin = 2022-06-20 12:02:28.718338652+00:00
start-sync_0 = 12:05:11
start-zstd = 12:05:28
start-sync_1 = 12:10:21
end-sync_1 = 12:10:39
end = 2022-06-20 12:10:39.191319448+00:00

[server]
repo = "cake233/node-arm64"

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
node = 'v18.4.0'
yarn = '1.22.19'
npm = '8.12.1'
```
