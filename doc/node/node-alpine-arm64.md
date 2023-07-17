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
tag = ["alpine", "2023-07-17", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_arm64_2023-07-17_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b380de87ca2643681fe9a24e6c13da9e430492194432c8e0ce428ab5d5367c91"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "198M"
tar_bytes = 207417856

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "35M"
zstd_bytes = 36107160

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230703"
previous_tag = "2023-07-03"
previous_file = "node-musl_arm64_2023-07-03_12-05-rootfs.tar.zst"
previous_sha256 = "6b51905e4bc05f30e94dc06ec26e8294f74526832413679f1e2c1c36741c122d"

current_version = "latest01"
current_date = "20230717"
old_file = "node-musl_arm64_2023-06-05_12-05-rootfs.tar.zst"
old_sha256 = "1ccaecb6dca73f1b7be1a7063b74c8ccbdb8b61b58d8f60a710e68877d01ec91"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node-musl_arm64_2023-07-17_12-05-rootfs.tar.zst
# SHA256SUM=b380de87ca2643681fe9a24e6c13da9e430492194432c8e0ce428ab5d5367c91
# BUILD_DATE=20230717
# BUILD_TAG=2023-07-17
# STATUS=completed
# VERSION=latest01
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-17
begin = 2023-07-17 12:02:37.452049113+00:00
start-sync_0 = 12:03:39
start-zstd = 12:03:47
start-sync_1 = 12:05:18
end-sync_1 = 12:05:26
end = 2023-07-17 12:05:26.353824183+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.4'
node = 'v20.4.0'
yarn = '1.22.19'
npm = '9.7.2'
```
