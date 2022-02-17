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
tag = ["zsh", "2022-02-17"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "kali-zsh_amd64_2022-02-17_12-08.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "39760a66a2c2239b591497542bd57438b87c1dd206a776350cebba9455a133ef"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "736M"
tar_bytes = 771620864

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "142M"
zstd_bytes = 148638016

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220210"
previous_tag = "2022-02-10"
previous_file = "kali-zsh_amd64_2022-02-10_12-09-rootfs.tar.zst"
previous_sha256 = "8bf4fbdd3399d6d1c9aefbccaad66f2b9347fd3270c9d0c95327bfdc8d75b1f4"

current_version = "latest01"
current_date = "20220217"
old_file = "kali-zsh_amd64_2022-02-03_12-09-rootfs.tar.zst"
old_sha256 = "b647ab9910486b49f572649eabfba94bea28aa86a1956e59c01b0ebc8bfefb0a"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2022-02-17_12-08-rootfs.tar.zst
# SHA256SUM=39760a66a2c2239b591497542bd57438b87c1dd206a776350cebba9455a133ef
# BUILD_DATE=20220217
# BUILD_TAG=2022-02-17
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-17
begin = 2022-02-17 12:02:25.119648734+00:00
start-sync_0 = 12:04:20
start-zstd = 12:06:04
start-sync_1 = 12:08:30
end-sync_1 = 12:08:43
end = 2022-02-17 12:08:43.421005781+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-1) 2.33'
zsh = 'zsh 5.8.1 (x86_64-debian-linux-gnu)'
```
