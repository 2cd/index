# ubuntu-kinetic-armv7

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-kinetic-armv7 \
    cake233/ubuntu-kinetic-armv7
```

## How to exec shell?

```sh
docker exec -it ubuntu-kinetic-armv7 sh
```

## ubuntu-kinetic-armv7.toml

```toml
[main]
name = "ubuntu"
tag = ["kinetic", "2022-05-12", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kinetic_armhf_2022-05-12_00-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a88f9d0fff8054fbad22a8ceda65dd48289bf03fd9c0e027c56ea462c768cc5e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "383M"
tar_bytes = 401459200

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "67M"
zstd_bytes = 69609074

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220511"
previous_tag = "2022-05-11"
previous_file = "ubuntu-kinetic_armhf_2022-05-11_00-11-rootfs.tar.zst"
previous_sha256 = "7d41a5c24c56cae873455ff95dcb22178f12c1724e9f77653f75d39841016c66"

current_version = "latest01"
current_date = "20220512"
old_file = "ubuntu-kinetic_armhf_2022-05-10_00-11-rootfs.tar.zst"
old_sha256 = "6d076fccd7da769b6b0671741a587c0cba07d21864c80a55074d0d2f6141a7c8"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-kinetic_armhf_2022-05-12_00-10-rootfs.tar.zst
# SHA256SUM=a88f9d0fff8054fbad22a8ceda65dd48289bf03fd9c0e027c56ea462c768cc5e
# BUILD_DATE=20220512
# BUILD_TAG=2022-05-12
# STATUS=completed
# VERSION=latest01
# END_TIME=00:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-12
begin = 2022-05-12 00:04:21.087869557+00:00
start-sync_0 = 00:08:57
start-zstd = 00:09:20
start-sync_1 = 00:10:30
end-sync_1 = 00:10:39
end = 2022-05-12 00:10:39.317699977+00:00

[server]
repo = "cake233/ubuntu-kinetic-armv7"

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
