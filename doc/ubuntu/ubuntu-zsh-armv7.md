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
tag = ["zsh", "2021-12-21", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "ubuntu-zsh_armhf_2021-12-21_00-19.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "60f26ddbded0a77b55decfa45d920050127e1ffabc284928cba3e49da68a3f05"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "572M"
tar_bytes = 598942720

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "107M"
zstd_bytes = 111756021

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211214"
previous_tag = "2021-12-14"
previous_file = "ubuntu-zsh_armhf_2021-12-14_00-17-rootfs.tar.zst"
previous_sha256 = "8db791d239f095e9bdc4ad9d02aea86071af60814e0f8b57cc5c63d9fc73b6f2"

current_version = "latest01"
current_date = "20211221"
old_file = "ubuntu-zsh_armhf_2021-12-07_00-15-rootfs.tar.zst"
old_sha256 = "f97383195e3ad3df3e4a39faa3c48ccb2d16571026ea096af3adc062f4472054"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-zsh_armhf_2021-12-21_00-19-rootfs.tar.zst
# SHA256SUM=60f26ddbded0a77b55decfa45d920050127e1ffabc284928cba3e49da68a3f05
# BUILD_DATE=20211221
# BUILD_TAG=2021-12-21
# STATUS=completed
# VERSION=latest01
# END_TIME=00:19

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-21
begin = 2021-12-21 00:02:28.123745110+00:00
start-sync_0 = 00:15:55
start-zstd = 00:17:37
start-sync_1 = 00:19:40
end-sync_1 = 00:19:52
end = 2021-12-21 00:19:52.358449396+00:00

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
