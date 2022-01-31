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
tag = ["alpine", "2022-01-31", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "node-musl_amd64_2022-01-31_12-04.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "fc5bf020500f3ab2d4d7302bdc28f42e575ab6aa96261dc6ccac2ffce8ced83b"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "182M"
tar_bytes = 189937152

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "34M"
zstd_bytes = 34906596

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220117"
previous_tag = "2022-01-17"
previous_file = "node-musl_amd64_2022-01-17_12-03-rootfs.tar.zst"
previous_sha256 = "310d437929b4079ff196bf33b07e4ddbbb14bd13fdcfcaa54b7adf96520989c8"

current_version = "latest02"
current_date = "20220131"
old_file = "node-musl_amd64_2022-01-03_12-03-rootfs.tar.zst"
old_sha256 = "8a51e040d8db281993cec5ba2822b93498655bf3b6bcb5855ba6f54755ed2143"
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node-musl_amd64_2022-01-31_12-04-rootfs.tar.zst
# SHA256SUM=fc5bf020500f3ab2d4d7302bdc28f42e575ab6aa96261dc6ccac2ffce8ced83b
# BUILD_DATE=20220131
# BUILD_TAG=2022-01-31
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-31
begin = 2022-01-31 12:02:29.527586499+00:00
start-sync_0 = 12:03:14
start-zstd = 12:03:28
start-sync_1 = 12:03:57
end-sync_1 = 12:04:08
end = 2022-01-31 12:04:08.357202890+00:00

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
node = 'v17.4.0'
yarn = '1.22.17'
npm = '8.3.1'
```
