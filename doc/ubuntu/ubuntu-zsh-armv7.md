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
tag = ["zsh", "2022-10-04", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_armhf_2022-10-04_00-23.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1604e780b5fafec4be78c1c1d06fdcc6577c2c0ae721144665a327e7004325c4"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "666M"
tar_bytes = 697903104

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "127M"
zstd_bytes = 133022000

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220927"
previous_tag = "2022-09-27"
previous_file = "ubuntu-zsh_armhf_2022-09-27_00-19-rootfs.tar.zst"
previous_sha256 = "27f92970a051dfd1c0f30e28853d7aca3e9a57ced3a7a988a374f0315d52230c"

current_version = "latest02"
current_date = "20221004"
old_file = "ubuntu-zsh_armhf_2022-09-20_00-18-rootfs.tar.zst"
old_sha256 = "0365e5799025405321b00c455947fe0d5b9d08b642e71b54c86fb581b037f91c"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-zsh_armhf_2022-10-04_00-23-rootfs.tar.zst
# SHA256SUM=1604e780b5fafec4be78c1c1d06fdcc6577c2c0ae721144665a327e7004325c4
# BUILD_DATE=20221004
# BUILD_TAG=2022-10-04
# STATUS=completed
# VERSION=latest02
# END_TIME=00:23

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-04
begin = 2022-10-04 00:02:27.767735453+00:00
start-sync_0 = 00:18:27
start-zstd = 00:20:19
start-sync_1 = 00:22:44
end-sync_1 = 00:23:03
end = 2022-10-04 00:23:03.714634997+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu3) 2.36'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```
