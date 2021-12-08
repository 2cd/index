# node-alpine-armv7

## How to run it?

```shell
docker run \
    -it \
    --name node-alpine-armv7 \
    cake233/node-alpine-armv7
```

## How to exec shell?

```shell
    docker exec -it node-alpine-armv7 bash
```

## node-alpine-armv7.toml

```toml
[main]
name = "node"
tag = ["alpine", "2021-12-06", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "node-musl_armhf_2021-12-06_20-06.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "c63bfe2b6066a4949f0cf94fa279873b157dccce2d1c26eeee02c3c78abdef00"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "167M"
tar_bytes = 174298624

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "32M"
zstd_bytes = 33156717

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211128"
previous_tag = "2021-11-28"
previous_file = "node-musl_armhf_2021-11-28_23-02-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211206"
old_file = ""
# edition 2021
# DISTRO_NAME=node_armhf
# ROOTFS_FILE=node-musl_armhf_2021-12-06_20-06-rootfs.tar.zst
# BUILD_DATE=20211206
# BUILD_TAG=2021-12-06
# STATUS=completed
# VERSION=latest02
# END_TIME=20:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-06
begin = 2021-12-06 20:04:30.035155229+00:00
start-sync_0 = 20:05:36
start-zstd = 20:05:47
start-sync_1 = 20:06:08
end-sync_1 = 20:06:22
end = 2021-12-06 20:06:22.674365555+00:00

[server]
repo = "cake233/node-alpine-armv7"

[server.node1]
name = "cn"
current = false
previous = true
in_sync = false
split = false

[server.node2]
name = "us"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "global"
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
node = 'v17.2.0'
yarn = '1.22.15'
npm = '8.1.4'
```
