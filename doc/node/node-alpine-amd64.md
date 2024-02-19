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
tag = ["alpine", "2024-02-19", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node-musl_amd64_2024-02-19_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8e3e222b576c81d0748cd68515c7f5dd552b81031f8dd1f508b93ad34c1773b1"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "153M"
tar_bytes = 160315904

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "37M"
zstd_bytes = 38029107

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231120"
previous_tag = "2023-11-20"
previous_file = "node-musl_amd64_2023-11-20_12-05-rootfs.tar.zst"
previous_sha256 = "b3d4429eb22a4bcd975af5bd44ef864b9c1dd7742bd9b81cb6d693e7dd5a2f26"

current_version = "latest02"
current_date = "20240219"
old_file = "node-musl_amd64_2023-10-23_12-05-rootfs.tar.zst"
old_sha256 = "83df5b06e66ab92b35277cf897d6986dcf52221a4697ae791087afb41d8db5af"
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node-musl_amd64_2024-02-19_12-05-rootfs.tar.zst
# SHA256SUM=8e3e222b576c81d0748cd68515c7f5dd552b81031f8dd1f508b93ad34c1773b1
# BUILD_DATE=20240219
# BUILD_TAG=2024-02-19
# STATUS=completed
# VERSION=latest02
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-19
begin = 2024-02-19 12:02:35.053530176+00:00
start-sync_0 = 12:04:01
start-zstd = 12:04:07
start-sync_1 = 12:05:10
end-sync_1 = 12:05:17
end = 2024-02-19 12:05:17.596595309+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.4_git20230717'
node = 'v21.6.2'
yarn = '1.22.19'
npm = '10.2.4'
```
