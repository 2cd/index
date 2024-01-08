# node-arm64

## How to run it?

```sh
docker run \
    -it \
    --name node-arm64 \
    cake233/node-arm64
```

## How to exec shell?

```sh
docker exec -it node-arm64 bash
```

## node-arm64.toml

```toml
[main]
name = "node"
tag = ["latest", "2024-01-08"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_arm64_2024-01-08_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "dc01011c7e45083570ec388312e40dc404a4ef0b9d3f03eb25c6dc503f71cfb8"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1154976768

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "212M"
zstd_bytes = 221659002

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
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node_arm64_2024-01-08_12-09-rootfs.tar.zst
# SHA256SUM=dc01011c7e45083570ec388312e40dc404a4ef0b9d3f03eb25c6dc503f71cfb8
# BUILD_DATE=20240108
# BUILD_TAG=2024-01-08
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-08
begin = 2024-01-08 12:02:35.061430395+00:00
start-sync_0 = 12:04:24
start-zstd = 12:04:40
start-sync_1 = 12:09:33
end-sync_1 = 12:09:51
end = 2024-01-08 12:09:51.174384088+00:00

[server]
repo = "cake233/node-arm64"

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
