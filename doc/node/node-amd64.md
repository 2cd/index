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
tag = ["latest", "2023-08-28"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_amd64_2023-08-28_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "13681def13f0248d057629a9cd735954a585a441907c65e7985873031dabd4c9"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1148478976

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "212M"
zstd_bytes = 221881906

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230828"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node_amd64_2023-08-28_12-12-rootfs.tar.zst
# SHA256SUM=13681def13f0248d057629a9cd735954a585a441907c65e7985873031dabd4c9
# BUILD_DATE=20230828
# BUILD_TAG=2023-08-28
# STATUS=completed
# VERSION=latest01
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-28
begin = 2023-08-28 12:02:41.059637473+00:00
start-sync_0 = 12:03:36
start-zstd = 12:03:56
start-sync_1 = 12:11:42
end-sync_1 = 12:12:03
end = 2023-08-28 12:12:03.899892159+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u1) 2.36'
node = 'v20.5.1'
yarn = '1.22.19'
npm = '9.8.0'
```