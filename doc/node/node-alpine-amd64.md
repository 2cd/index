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
tag = ["alpine", "2022-04-25", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "node-musl_amd64_2022-04-25_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "dc28fcd914a2c62bed79315d6a2cbbd7c4ba15cc771a1615038dff94597344df"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "184M"
tar_bytes = 191897600

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "32M"
zstd_bytes = 33513024

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220411"
previous_tag = "2022-04-11"
previous_file = "node-musl_amd64_2022-04-11_11-04-rootfs.tar.zst"
previous_sha256 = "9b516970c9199ca1d3404fd95e3adb96e0ff37d443b3a594d528c20d37a6332b"

current_version = "latest01"
current_date = "20220425"
old_file = "node-musl_amd64_2022-03-28_11-04-rootfs.tar.zst"
old_sha256 = "64393efb345ec25e51c301b605a5674ab6660d7426838e3d49851c0052879d5b"
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node-musl_amd64_2022-04-25_12-04-rootfs.tar.zst
# SHA256SUM=dc28fcd914a2c62bed79315d6a2cbbd7c4ba15cc771a1615038dff94597344df
# BUILD_DATE=20220425
# BUILD_TAG=2022-04-25
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-25
begin = 2022-04-25 12:02:32.957869948+00:00
start-sync_0 = 12:03:13
start-zstd = 12:03:27
start-sync_1 = 12:04:25
end-sync_1 = 12:04:36
end = 2022-04-25 12:04:36.307515347+00:00

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
node = 'v18.0.0'
yarn = '1.22.18'
npm = '8.6.0'
```
