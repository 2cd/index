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
tag = ["latest", "2023-10-09"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_amd64_2023-10-09_12-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "28e638d6f10697b0dccf32a87ce5082cf733bcc3ba1fd64cead8d0406c4f8b3b"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1150326272

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "212M"
zstd_bytes = 222025374

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230925"
previous_tag = "2023-09-25"
previous_file = "node_amd64_2023-09-25_12-10-rootfs.tar.zst"
previous_sha256 = "339dff13eea0cf9415ced410a3c51c9de67e270814d3ced314973844d2d66087"

current_version = "latest02"
current_date = "20231009"
old_file = "node_amd64_2023-09-11_12-11-rootfs.tar.zst"
old_sha256 = "f674cad2eb312642dfd4a6ed3ff2c13361df4a5ea5ac819ebf69fdf2f8297ccf"
# edition 2021
# DISTRO_NAME=node_amd64
# ROOTFS_FILE=node_amd64_2023-10-09_12-13-rootfs.tar.zst
# SHA256SUM=28e638d6f10697b0dccf32a87ce5082cf733bcc3ba1fd64cead8d0406c4f8b3b
# BUILD_DATE=20231009
# BUILD_TAG=2023-10-09
# STATUS=completed
# VERSION=latest02
# END_TIME=12:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-09
begin = 2023-10-09 12:02:34.792802672+00:00
start-sync_0 = 12:04:49
start-zstd = 12:06:58
start-sync_1 = 12:13:34
end-sync_1 = 12:13:55
end = 2023-10-09 12:13:55.990542613+00:00

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
node = 'v20.8.0'
yarn = '1.22.19'
npm = '10.1.0'
```
