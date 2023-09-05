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
tag = ["alpine", "2023-08-28", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_amd64_2023-08-28_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "142e6810b337e197f2c5757f7423c86e8b0f67f13aa552953c0abc0ac57d2097"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "192M"
tar_bytes = 201177600

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "35M"
zstd_bytes = 36511959

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230828"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node-musl_amd64_2023-08-28_12-04-rootfs.tar.zst
# SHA256SUM=142e6810b337e197f2c5757f7423c86e8b0f67f13aa552953c0abc0ac57d2097
# BUILD_DATE=20230828
# BUILD_TAG=2023-08-28
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-28
begin = 2023-08-28 12:02:39.955282499+00:00
start-sync_0 = 12:02:59
start-zstd = 12:03:09
start-sync_1 = 12:04:26
end-sync_1 = 12:04:33
end = 2023-08-28 12:04:33.221398215+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.4'
node = 'v20.5.1'
yarn = '1.22.19'
npm = '9.8.0'
```