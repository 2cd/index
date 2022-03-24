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
tag = ["alpine", "2022-03-24", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "node-musl_amd64_2022-03-24_12-29.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "3a2b31d52c72b239cacae0413899ae048cd4d8c4b76e50e0707f6057e1d82388"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "180M"
tar_bytes = 188227072

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "32M"
zstd_bytes = 32953859

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220314"
previous_tag = "2022-03-14"
previous_file = "node-musl_amd64_2022-03-14_12-04-rootfs.tar.zst"
previous_sha256 = "e384942d09c08c65d648820863283e8b1a2d7b02073200433a01da2f80b964c6"

current_version = "latest02"
current_date = "20220324"
old_file = "node-musl_amd64_2022-03-01_18-55-rootfs.tar.zst"
old_sha256 = "7879f26644621eeb3ef67cde51ccca6902d8565a67c789bda67bc4e56977814a"
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node-musl_amd64_2022-03-24_12-29-rootfs.tar.zst
# SHA256SUM=3a2b31d52c72b239cacae0413899ae048cd4d8c4b76e50e0707f6057e1d82388
# BUILD_DATE=20220324
# BUILD_TAG=2022-03-24
# STATUS=completed
# VERSION=latest02
# END_TIME=12:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-24
begin = 2022-03-24 12:27:07.997153136+00:00
start-sync_0 = 12:27:47
start-zstd = 12:27:55
start-sync_1 = 12:28:59
end-sync_1 = 12:29:06
end = 2022-03-24 12:29:06.270848685+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
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
ldd = 'musl libc (x86_64) Version 1.2.2'
node = 'v17.8.0'
yarn = '1.22.18'
npm = '8.5.5'
```
