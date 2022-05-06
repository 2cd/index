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
tag = ["kinetic", "2022-05-06", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kinetic_armhf_2022-05-06_00-33.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "cb973c25fd34abdda6ec991f4781ae791bc424e354e504b3b72f0f6c3a29e31f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "383M"
tar_bytes = 401460736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "67M"
zstd_bytes = 69734703

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220505"
previous_tag = "2022-05-05"
previous_file = "ubuntu-kinetic_armhf_2022-05-05_00-24-rootfs.tar.zst"
previous_sha256 = "26652ef00f9b7fbd1589bdee355a7931a02bfc8ec8b9c0d370487769a3938ccb"

current_version = "latest02"
current_date = "20220506"
old_file = "ubuntu-kinetic_armhf_2022-05-04_00-12-rootfs.tar.zst"
old_sha256 = "faccf92d0cadab503f82bd8766f537ec685dfb996e0720f915ccc7fd5923182a"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-kinetic_armhf_2022-05-06_00-33-rootfs.tar.zst
# SHA256SUM=cb973c25fd34abdda6ec991f4781ae791bc424e354e504b3b72f0f6c3a29e31f
# BUILD_DATE=20220506
# BUILD_TAG=2022-05-06
# STATUS=completed
# VERSION=latest02
# END_TIME=00:33

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-06
begin = 2022-05-06 00:27:41.773375116+00:00
start-sync_0 = 00:32:13
start-zstd = 00:32:37
start-sync_1 = 00:33:40
end-sync_1 = 00:33:50
end = 2022-05-06 00:33:50.497627238+00:00

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
