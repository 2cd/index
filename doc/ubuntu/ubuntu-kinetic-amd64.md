# ubuntu-kinetic-amd64

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-kinetic-amd64 \
    cake233/ubuntu-kinetic-amd64
```

## How to exec shell?

```sh
docker exec -it ubuntu-kinetic-amd64 sh
```

## ubuntu-kinetic-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["kinetic", "2022-04-27", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kinetic_amd64_2022-04-27_13-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5cf855278f6616b2e83715e5e7ab255f622b81e1d251b97d60fd7b68b7dbb4a1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "418M"
tar_bytes = 438179840

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "70M"
zstd_bytes = 73104776

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220427"
previous_tag = "2022-04-27"
previous_file = "ubuntu-kinetic_amd64_2022-04-27_00-10-rootfs.tar.zst"
previous_sha256 = "a6850a33abf45fdf77f9a155a1385913839966f83928f01d51f39e0dfb2e0563"

current_version = "latest02"
current_date = "20220427"
old_file = "ubuntu-kinetic_amd64_2022-04-26_00-07-rootfs.tar.zst"
old_sha256 = "63de3f4853258d34aac5476f80de67536057572f293e78951147a69d931de17f"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kinetic_amd64_2022-04-27_13-14-rootfs.tar.zst
# SHA256SUM=5cf855278f6616b2e83715e5e7ab255f622b81e1d251b97d60fd7b68b7dbb4a1
# BUILD_DATE=20220427
# BUILD_TAG=2022-04-27
# STATUS=completed
# VERSION=latest02
# END_TIME=13:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-27
begin = 2022-04-27 13:12:17.750387266+00:00
start-sync_0 = 13:12:59
start-zstd = 13:13:23
start-sync_1 = 13:14:37
end-sync_1 = 13:14:48
end = 2022-04-27 13:14:48.773085736+00:00

[server]
repo = "cake233/ubuntu-kinetic-amd64"

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
```
