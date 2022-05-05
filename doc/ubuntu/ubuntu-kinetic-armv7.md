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
tag = ["kinetic", "2022-05-05", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kinetic_armhf_2022-05-05_00-24.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "26652ef00f9b7fbd1589bdee355a7931a02bfc8ec8b9c0d370487769a3938ccb"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "383M"
tar_bytes = 401464832

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "67M"
zstd_bytes = 69637741

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220504"
previous_tag = "2022-05-04"
previous_file = "ubuntu-kinetic_armhf_2022-05-04_00-12-rootfs.tar.zst"
previous_sha256 = "faccf92d0cadab503f82bd8766f537ec685dfb996e0720f915ccc7fd5923182a"

current_version = "latest01"
current_date = "20220505"
old_file = "ubuntu-kinetic_armhf_2022-05-03_00-11-rootfs.tar.zst"
old_sha256 = "f27792ee57b70c5985d81bf64f6f2f3aefede173eef85f44be47ea264b2c582c"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-kinetic_armhf_2022-05-05_00-24-rootfs.tar.zst
# SHA256SUM=26652ef00f9b7fbd1589bdee355a7931a02bfc8ec8b9c0d370487769a3938ccb
# BUILD_DATE=20220505
# BUILD_TAG=2022-05-05
# STATUS=completed
# VERSION=latest01
# END_TIME=00:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-05
begin = 2022-05-05 00:18:27.502502981+00:00
start-sync_0 = 00:22:55
start-zstd = 00:23:22
start-sync_1 = 00:24:27
end-sync_1 = 00:24:39
end = 2022-05-05 00:24:39.179146428+00:00

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
