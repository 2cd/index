# node-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name node-alpine-arm64 \
    cake233/node-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it node-alpine-arm64 bash
```

## node-alpine-arm64.toml

```toml
[main]
name = "node"
tag = ["alpine", "2023-05-08", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_arm64_2023-05-08_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8ce47d65fd2de6936994479e83cf4be934c9d441f1bfae2594d58d560ccd8b91"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "198M"
tar_bytes = 207027712

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "35M"
zstd_bytes = 36084136

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230424"
previous_tag = "2023-04-24"
previous_file = "node-musl_arm64_2023-04-24_12-05-rootfs.tar.zst"
previous_sha256 = "cd03bab313a8310d444056e12a65e6bf1f8ad7a390ca78cbd38338878c4240e5"

current_version = "latest01"
current_date = "20230508"
old_file = "node-musl_arm64_2023-04-10_12-05-rootfs.tar.zst"
old_sha256 = "0d3687adba866a2d65b29eba3725a9ce0e7e9b7c8c88a4a3444ee7823bda8fcc"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node-musl_arm64_2023-05-08_12-05-rootfs.tar.zst
# SHA256SUM=8ce47d65fd2de6936994479e83cf4be934c9d441f1bfae2594d58d560ccd8b91
# BUILD_DATE=20230508
# BUILD_TAG=2023-05-08
# STATUS=completed
# VERSION=latest01
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-08
begin = 2023-05-08 12:02:46.000235744+00:00
start-sync_0 = 12:04:19
start-zstd = 12:04:29
start-sync_1 = 12:05:47
end-sync_1 = 12:05:56
end = 2023-05-08 12:05:56.471669689+00:00

[server]
repo = "cake233/node-alpine-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.3'
node = 'v20.1.0'
yarn = '1.22.19'
npm = '9.6.4'
```
