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
tag = ["latest", "2022-12-05"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_amd64_2022-12-05_12-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "47d780310385425ba7ce82c537104809079454e0f9c205b10d12f27048c54ebd"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "996M"
tar_bytes = 1043874816

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "200M"
zstd_bytes = 209017044

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221121"
previous_tag = "2022-11-21"
previous_file = "node_amd64_2022-11-21_12-15-rootfs.tar.zst"
previous_sha256 = "f37a54f4c49a8d5c573e9e91dc57acb2e8fce7603680cbe45d71d0e1042d512b"

current_version = "latest01"
current_date = "20221205"
old_file = "node_amd64_2022-11-07_12-16-rootfs.tar.zst"
old_sha256 = "e11bf4f7a6514d5fdf34880310db70ac0df32de17b69227334917b705fc3f1a5"
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node_amd64_2022-12-05_12-13-rootfs.tar.zst
# SHA256SUM=47d780310385425ba7ce82c537104809079454e0f9c205b10d12f27048c54ebd
# BUILD_DATE=20221205
# BUILD_TAG=2022-12-05
# STATUS=completed
# VERSION=latest01
# END_TIME=12:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-05
begin = 2022-12-05 12:02:29.480556061+00:00
start-sync_0 = 12:03:33
start-zstd = 12:04:47
start-sync_1 = 12:12:51
end-sync_1 = 12:13:07
end = 2022-12-05 12:13:07.325738772+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
node = 'v19.2.0'
yarn = '1.22.19'
npm = '8.19.3'
```
