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
tag = ["latest", "2022-09-26"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_amd64_2022-09-26_12-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "15b33dff905da0f1e4fc33360411268633496af8bc66b8239c9e0157f868282b"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "992M"
tar_bytes = 1039913472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "199M"
zstd_bytes = 208122946

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220912"
previous_tag = "2022-09-12"
previous_file = "node_amd64_2022-09-12_12-13-rootfs.tar.zst"
previous_sha256 = "1f5856980c7e98a2c7c0996899423d087bd2d842e0c8bab1539c324c01a81ecb"

current_version = "latest02"
current_date = "20220926"
old_file = "node_amd64_2022-08-29_12-14-rootfs.tar.zst"
old_sha256 = "42e9e2041de65b09fdbb83c7e734e0affd650c74ca3b43002f84953573fd04ac"
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node_amd64_2022-09-26_12-16-rootfs.tar.zst
# SHA256SUM=15b33dff905da0f1e4fc33360411268633496af8bc66b8239c9e0157f868282b
# BUILD_DATE=20220926
# BUILD_TAG=2022-09-26
# STATUS=completed
# VERSION=latest02
# END_TIME=12:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-26
begin = 2022-09-26 12:02:27.918629036+00:00
start-sync_0 = 12:04:17
start-zstd = 12:06:19
start-sync_1 = 12:16:07
end-sync_1 = 12:16:24
end = 2022-09-26 12:16:24.392541896+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u4) 2.31'
node = 'v18.9.0'
yarn = '1.22.19'
npm = '8.19.1'
```
