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
tag = ["zsh", "2022-03-15", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "ubuntu-zsh_armhf_2022-03-15_00-17.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "d69ce0b257af7b6f4e6e6075412d2bb14f6ecf43c1bb1c714341ea3fc34aa77a"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "575M"
tar_bytes = 602671104

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "109M"
zstd_bytes = 113391486

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220308"
previous_tag = "2022-03-08"
previous_file = "ubuntu-zsh_armhf_2022-03-08_00-20-rootfs.tar.zst"
previous_sha256 = "5872fc14586c987df2c7481298a852187bf194a8feccd5e449682bd4b714f75e"

current_version = "latest02"
current_date = "20220315"
old_file = "ubuntu-zsh_armhf_2022-03-01_00-23-rootfs.tar.zst"
old_sha256 = "50c76dd81dc2a52f89fe6fd8e88b7b11860d31cc640c68b729397895c7cba031"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-zsh_armhf_2022-03-15_00-17-rootfs.tar.zst
# SHA256SUM=d69ce0b257af7b6f4e6e6075412d2bb14f6ecf43c1bb1c714341ea3fc34aa77a
# BUILD_DATE=20220315
# BUILD_TAG=2022-03-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-15
begin = 2022-03-15 00:02:28.449020922+00:00
start-sync_0 = 00:13:53
start-zstd = 00:15:38
start-sync_1 = 00:17:33
end-sync_1 = 00:17:47
end = 2022-03-15 00:17:47.266027943+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.8.1 (arm-unknown-linux-gnueabihf)'
```
