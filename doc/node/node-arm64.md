# node-arm64

## How to run it?

```shell
docker run \
    -it \
    --name node-arm64 \
    cake233/node-arm64
```

## How to exec shell?

```shell
    docker exec -it node-arm64 bash
```

## node-arm64.toml

```toml
[main]
name = "node"
tag = ["latest", "2021-11-28"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "node_arm64_2021-11-28_23-07.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "4fdf27466cf90141c8ee82ade1ab4c53816dc93b35ca8acbac8a0948b7e68b8c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "947M"
tar_bytes = 992163328

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "205M"
zstd_bytes = 214835812

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211101"
last_tag = ""
last_file = "node_arm64+latest-2021_11-01-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211128"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node_arm64_2021-11-28_23-07-rootfs.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest02
# END_TIME=23:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 23:01:38.792354087+00:00
start-sync_0 = 23:03:50
start-zstd = 23:04:07
start-sync_1 = 23:07:14
end-sync_1 = 23:07:33
end = 2021-11-28 23:07:33.982888759+00:00

[server]
repo = "cake233/node-arm64"

[server.node1]
name = "cn"
current = false
last = true
split = false

[server.node2]
name = "us"
current = false
last = true
split = false
part = 12

[server.node3]
name = "global"
current = false
last = true
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"

[version]
node = 'v17.1.0'
yarn = '1.22.15'
npm = '8.1.2'
```
