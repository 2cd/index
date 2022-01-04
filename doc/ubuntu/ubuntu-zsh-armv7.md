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
tag = ["zsh", "2022-01-04", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "ubuntu-zsh_armhf_2022-01-04_00-22.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "5982d1c39674088025c494ee9e398da689c206747b910b755f383daa70d7a521"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "573M"
tar_bytes = 600357888

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "107M"
zstd_bytes = 112095505

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211228"
previous_tag = "2021-12-28"
previous_file = "ubuntu-zsh_armhf_2021-12-28_00-20-rootfs.tar.zst"
previous_sha256 = "09acdd6369aed9024f4e5b2cce54f19010fa4a4f5d1451f22939fa490a67044e"

current_version = "latest01"
current_date = "20220104"
old_file = "ubuntu-zsh_armhf_2021-12-21_00-19-rootfs.tar.zst"
old_sha256 = "60f26ddbded0a77b55decfa45d920050127e1ffabc284928cba3e49da68a3f05"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-zsh_armhf_2022-01-04_00-22-rootfs.tar.zst
# SHA256SUM=5982d1c39674088025c494ee9e398da689c206747b910b755f383daa70d7a521
# BUILD_DATE=20220104
# BUILD_TAG=2022-01-04
# STATUS=completed
# VERSION=latest01
# END_TIME=00:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-04
begin = 2022-01-04 00:02:29.699025048+00:00
start-sync_0 = 00:17:42
start-zstd = 00:19:34
start-sync_1 = 00:22:01
end-sync_1 = 00:22:19
end = 2022-01-04 00:22:19.038188539+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (Ubuntu GLIBC 2.34-0ubuntu3) 2.34'
zsh = 'zsh 5.8 (arm-unknown-linux-gnueabihf)'
```
