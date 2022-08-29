# node-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name node-alpine-amd64 \
    cake233/node-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it node-alpine-amd64 bash
```

## node-alpine-amd64.toml

```toml
[main]
name = "node"
tag = ["alpine", "2022-08-29", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_amd64_2022-08-29_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0d7f3e27036087e9a32b3b52abe4db00011a38639d02d41e0a101c587d03bf50"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "178M"
tar_bytes = 186525696

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "33M"
zstd_bytes = 34060533

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220815"
previous_tag = "2022-08-15"
previous_file = "node-musl_amd64_2022-08-15_12-04-rootfs.tar.zst"
previous_sha256 = "9c79e9326be4d393ea4306f3f44ccbe81d470d65fb45db50082cdca6b8efbb5b"

current_version = "latest02"
current_date = "20220829"
old_file = "node-musl_amd64_2022-07-04_12-04-rootfs.tar.zst"
old_sha256 = "c1527f2e5930ef6dbbc94cc9744f5229b5097fc82a53698b02b5c3c6b57a55a1"
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node-musl_amd64_2022-08-29_12-05-rootfs.tar.zst
# SHA256SUM=0d7f3e27036087e9a32b3b52abe4db00011a38639d02d41e0a101c587d03bf50
# BUILD_DATE=20220829
# BUILD_TAG=2022-08-29
# STATUS=completed
# VERSION=latest02
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-29
begin = 2022-08-29 12:02:28.935506888+00:00
start-sync_0 = 12:03:44
start-zstd = 12:03:55
start-sync_1 = 12:05:08
end-sync_1 = 12:05:17
end = 2022-08-29 12:05:17.692010218+00:00

[server]
repo = "cake233/node-alpine-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.3'
node = 'v18.8.0'
yarn = '1.22.19'
npm = '8.18.0'
```
