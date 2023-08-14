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
tag = ["latest", "2023-08-14"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_amd64_2023-08-14_12-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f3e06bba89d21430c5ccbb1d018eb33a7e25d2394ec78c11eef48c35471e5196"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1148542976

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "212M"
zstd_bytes = 221842881

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230731"
previous_tag = "2023-07-31"
previous_file = "node_amd64_2023-07-31_12-10-rootfs.tar.zst"
previous_sha256 = "8a743dee267caaaa1609344eaf2288ea9d913ab20c7bf9006e08310642fb7728"

current_version = "latest02"
current_date = "20230814"
old_file = "node_amd64_2023-07-17_12-13-rootfs.tar.zst"
old_sha256 = "5f10ab8c873a17b06106f2f02285f21405795fdbd29683aa20952165aeb274d9"
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node_amd64_2023-08-14_12-20-rootfs.tar.zst
# SHA256SUM=f3e06bba89d21430c5ccbb1d018eb33a7e25d2394ec78c11eef48c35471e5196
# BUILD_DATE=20230814
# BUILD_TAG=2023-08-14
# STATUS=completed
# VERSION=latest02
# END_TIME=12:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-14
begin = 2023-08-14 12:02:39.762071550+00:00
start-sync_0 = 12:06:03
start-zstd = 12:13:14
start-sync_1 = 12:20:25
end-sync_1 = 12:20:51
end = 2023-08-14 12:20:51.544245700+00:00

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
