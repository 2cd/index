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
tag = ["latest", "2023-03-13"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_arm64_2023-03-13_12-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e667461400729b4a3054c67d0192e904bebf4968fa0354db862b4052c79aa013"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "952M"
tar_bytes = 997980672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "198M"
zstd_bytes = 207410879

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230227"
previous_tag = "2023-02-27"
previous_file = "node_arm64_2023-02-27_12-11-rootfs.tar.zst"
previous_sha256 = "d53879a3b1be12a9d5ba54c3b78148e0f6f89c26d89331c45bbf8737c873af36"

current_version = "latest01"
current_date = "20230313"
old_file = "node_arm64_2023-02-13_12-11-rootfs.tar.zst"
old_sha256 = "b547f89a0b27e7ccab6be973522c949955f8086aa6ba68636c3c5dd49e59091b"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node_arm64_2023-03-13_12-13-rootfs.tar.zst
# SHA256SUM=e667461400729b4a3054c67d0192e904bebf4968fa0354db862b4052c79aa013
# BUILD_DATE=20230313
# BUILD_TAG=2023-03-13
# STATUS=completed
# VERSION=latest01
# END_TIME=12:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-13
begin = 2023-03-13 12:02:42.329698746+00:00
start-sync_0 = 12:06:53
start-zstd = 12:07:15
start-sync_1 = 12:13:06
end-sync_1 = 12:13:29
end = 2023-03-13 12:13:29.512160764+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
node = 'v19.7.0'
yarn = '1.22.19'
npm = '9.5.0'
```
