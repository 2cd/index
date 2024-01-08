# node-amd64

## How to run it?

```sh
docker run \
    -it \
    --name node-amd64 \
    cake233/node-amd64
```

## How to exec shell?

```sh
docker exec -it node-amd64 bash
```

## node-amd64.toml

```toml
[main]
name = "node"
tag = ["latest", "2024-01-08"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_amd64_2024-01-08_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1b04380ae2cfc0a02b9d5084b477f7f8480132e2589df0fadc130a8593ba573a"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1154723840

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "213M"
zstd_bytes = 223311096

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20240108"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node_amd64_2024-01-08_12-08-rootfs.tar.zst
# SHA256SUM=1b04380ae2cfc0a02b9d5084b477f7f8480132e2589df0fadc130a8593ba573a
# BUILD_DATE=20240108
# BUILD_TAG=2024-01-08
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-08
begin = 2024-01-08 12:02:37.425867675+00:00
start-sync_0 = 12:03:12
start-zstd = 12:03:27
start-sync_1 = 12:08:22
end-sync_1 = 12:08:40
end = 2024-01-08 12:08:40.300121264+00:00

[server]
repo = "cake233/node-amd64"

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u3) 2.36'
node = 'v21.5.0'
yarn = '1.22.19'
npm = '10.2.4'
```
