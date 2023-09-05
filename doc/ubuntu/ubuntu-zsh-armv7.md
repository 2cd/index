# ubuntu-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-zsh-armv7 \
    cake233/ubuntu-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it ubuntu-zsh-armv7 zsh
```

## ubuntu-zsh-armv7.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2023-09-05", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_armhf_2023-09-05_00-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b77b1cd0baa490f8d4adbf93ad448d00764fb4ed2c0f8c295476cbb1e42ee618"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "707M"
tar_bytes = 740719104

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "149M"
zstd_bytes = 155539223

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230829"
previous_tag = "2023-08-29"
previous_file = "ubuntu-zsh_armhf_2023-08-29_00-28-rootfs.tar.zst"
previous_sha256 = "d05a3ee278c86ec39d39b63b2e3d53961c9e33a0ea87125978873c4024d5ee58"

current_version = "latest01"
current_date = "20230905"
old_file = "ubuntu-zsh_armhf_2023-08-22_00-19-rootfs.tar.zst"
old_sha256 = "cf2eb56e97f9324f50a10ef067e0724116fe7c052a329d23a1215e97cfd5f02b"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-zsh_armhf_2023-09-05_00-28-rootfs.tar.zst
# SHA256SUM=b77b1cd0baa490f8d4adbf93ad448d00764fb4ed2c0f8c295476cbb1e42ee618
# BUILD_DATE=20230905
# BUILD_TAG=2023-09-05
# STATUS=completed
# VERSION=latest01
# END_TIME=00:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-05
begin = 2023-09-05 00:02:40.061986595+00:00
start-sync_0 = 00:23:08
start-zstd = 00:24:59
start-sync_1 = 00:27:44
end-sync_1 = 00:28:03
end = 2023-09-05 00:28:03.532629973+00:00

[server]
repo = "cake233/ubuntu-zsh-armv7"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu4) 2.38'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```