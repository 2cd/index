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
tag = ["latest", "2022-07-18"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_amd64_2022-07-18_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "05bc118a74bf61f033d305ebca95828905f480197f30b92d6f09370c2202fa2b"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "999M"
tar_bytes = 1047210496

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "199M"
zstd_bytes = 208001836

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220704"
previous_tag = "2022-07-04"
previous_file = "node_amd64_2022-07-04_12-13-rootfs.tar.zst"
previous_sha256 = "737f342a2ea9d57c010f4af19c366fbe9e7106674df741c4e769430765482736"

current_version = "latest01"
current_date = "20220718"
old_file = "node_amd64_2022-06-20_12-14-rootfs.tar.zst"
old_sha256 = "7b3df086953ecf605300c6723b1b3917dfbd289fe83211252cbec0c8c2532ff4"
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node_amd64_2022-07-18_12-12-rootfs.tar.zst
# SHA256SUM=05bc118a74bf61f033d305ebca95828905f480197f30b92d6f09370c2202fa2b
# BUILD_DATE=20220718
# BUILD_TAG=2022-07-18
# STATUS=completed
# VERSION=latest01
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-18
begin = 2022-07-18 12:02:28.644962193+00:00
start-sync_0 = 12:03:40
start-zstd = 12:03:55
start-sync_1 = 12:11:52
end-sync_1 = 12:12:10
end = 2022-07-18 12:12:10.358610914+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
node = 'v18.6.0'
yarn = '1.22.19'
npm = '8.13.2'
```
