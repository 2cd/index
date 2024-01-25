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
tag = ["zsh", "2024-01-25"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2024-01-25_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8ea204b010629dd2d628c409f7ef8ad96f385982e965762ca7c5729344ea9c25"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "786M"
tar_bytes = 823632896

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "155M"
zstd_bytes = 162011072

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231123"
previous_tag = "2023-11-23"
previous_file = "kali-zsh_amd64_2023-11-23_12-08-rootfs.tar.zst"
previous_sha256 = "49bd5b112a5355b9eacfecfbc04f4eda89eaf98a8445a0d500116ae927b2a4d4"

current_version = "latest01"
current_date = "20240125"
old_file = "kali-zsh_amd64_2023-11-16_12-08-rootfs.tar.zst"
old_sha256 = "00a8cb4233616488af98b82bf3d385faba3681c3076f7597a75965b97497ef6a"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2024-01-25_12-08-rootfs.tar.zst
# SHA256SUM=8ea204b010629dd2d628c409f7ef8ad96f385982e965762ca7c5729344ea9c25
# BUILD_DATE=20240125
# BUILD_TAG=2024-01-25
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-25
begin = 2024-01-25 12:02:37.251484960+00:00
start-sync_0 = 12:04:14
start-zstd = 12:05:58
start-sync_1 = 12:08:14
end-sync_1 = 12:08:30
end = 2024-01-25 12:08:30.536498203+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
