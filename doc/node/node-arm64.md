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
tag = ["latest", "2023-06-05"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_arm64_2023-06-05_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "19747a455cffbc63e9c7228873d5991fcbe5d474c2031933d87728e0d2eacf43"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "955M"
tar_bytes = 1001120768

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "199M"
zstd_bytes = 208403871

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230522"
previous_tag = "2023-05-22"
previous_file = "node_arm64_2023-05-22_12-11-rootfs.tar.zst"
previous_sha256 = "2d1e0cf0c4c23fa9b1f4d2cbe75ee87fe449d34a4cec0120eff23b53cf0436f1"

current_version = "latest01"
current_date = "20230605"
old_file = "node_arm64_2023-05-08_12-12-rootfs.tar.zst"
old_sha256 = "7a5b71a23614da11c994713ea865a412b13f3515dc54297c09a8ea4ccdd4040d"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node_arm64_2023-06-05_12-10-rootfs.tar.zst
# SHA256SUM=19747a455cffbc63e9c7228873d5991fcbe5d474c2031933d87728e0d2eacf43
# BUILD_DATE=20230605
# BUILD_TAG=2023-06-05
# STATUS=completed
# VERSION=latest01
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-05
begin = 2023-06-05 12:02:40.493501244+00:00
start-sync_0 = 12:05:37
start-zstd = 12:05:52
start-sync_1 = 12:10:25
end-sync_1 = 12:10:42
end = 2023-06-05 12:10:42.260583311+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u6) 2.31'
node = 'v20.2.0'
yarn = '1.22.19'
npm = '9.6.6'
```
