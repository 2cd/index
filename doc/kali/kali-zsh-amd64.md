# kali-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-amd64 \
    cake233/kali-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it kali-zsh-amd64 zsh
```

## kali-zsh-amd64.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2022-02-24"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "kali-zsh_amd64_2022-02-24_12-09.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "de4cd3fb91c47fec771f35908ac9b0f0c7d1bf4e83ce69db25637fbd60fdb41e"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "738M"
tar_bytes = 772988928

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "143M"
zstd_bytes = 148912083

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220217"
previous_tag = "2022-02-17"
previous_file = "kali-zsh_amd64_2022-02-17_12-08-rootfs.tar.zst"
previous_sha256 = "39760a66a2c2239b591497542bd57438b87c1dd206a776350cebba9455a133ef"

current_version = "latest02"
current_date = "20220224"
old_file = "kali-zsh_amd64_2022-02-10_12-09-rootfs.tar.zst"
old_sha256 = "8bf4fbdd3399d6d1c9aefbccaad66f2b9347fd3270c9d0c95327bfdc8d75b1f4"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2022-02-24_12-09-rootfs.tar.zst
# SHA256SUM=de4cd3fb91c47fec771f35908ac9b0f0c7d1bf4e83ce69db25637fbd60fdb41e
# BUILD_DATE=20220224
# BUILD_TAG=2022-02-24
# STATUS=completed
# VERSION=latest02
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-24
begin = 2022-02-24 12:02:31.205710840+00:00
start-sync_0 = 12:04:42
start-zstd = 12:06:32
start-sync_1 = 12:09:31
end-sync_1 = 12:09:47
end = 2022-02-24 12:09:47.760268871+00:00

[server]
repo = "cake233/kali-zsh-amd64"

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.8.1 (x86_64-debian-linux-gnu)'
```
