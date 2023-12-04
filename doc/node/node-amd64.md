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
tag = ["latest", "2023-12-04"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_amd64_2023-12-04_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a5309f23a3c40ccb836100ead1917f20489813bf83d3e290d3a2701d79520c11"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1154536448

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "213M"
zstd_bytes = 223124127

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231023"
previous_tag = "2023-10-23"
previous_file = "node_amd64_2023-10-23_12-12-rootfs.tar.zst"
previous_sha256 = "1f17bafda7a19b3f68c929fe502834f4f35bb1a07bae52871d1f8d1f9206bdfa"

current_version = "latest02"
current_date = "20231204"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node_amd64_2023-12-04_12-11-rootfs.tar.zst
# SHA256SUM=a5309f23a3c40ccb836100ead1917f20489813bf83d3e290d3a2701d79520c11
# BUILD_DATE=20231204
# BUILD_TAG=2023-12-04
# STATUS=completed
# VERSION=latest02
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-04
begin = 2023-12-04 12:02:34.623133463+00:00
start-sync_0 = 12:04:29
start-zstd = 12:06:09
start-sync_1 = 12:10:57
end-sync_1 = 12:11:12
end = 2023-12-04 12:11:12.991345565+00:00

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
node = 'v21.3.0'
yarn = '1.22.19'
npm = '10.2.4'
```
