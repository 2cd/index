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
tag = ["zsh", "2022-09-22"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2022-09-22_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "185b18f73b9687bbca80dcbfb2d5a091ba5ef3272ed8092eb0eff8b7ad979a82"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "757M"
tar_bytes = 793083392

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "148M"
zstd_bytes = 154533205

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220915"
previous_tag = "2022-09-15"
previous_file = "kali-zsh_amd64_2022-09-15_12-08-rootfs.tar.zst"
previous_sha256 = "837fe7d8a08d162777b152cde8a85726742c8cb5a37daffc010dc7b6af7d8491"

current_version = "latest01"
current_date = "20220922"
old_file = "kali-zsh_amd64_2022-09-08_12-09-rootfs.tar.zst"
old_sha256 = "8654e255f609f3963452cf7b0f9f8ce0ce38422a7caeff3d4ed8ad851eb5e07c"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2022-09-22_12-09-rootfs.tar.zst
# SHA256SUM=185b18f73b9687bbca80dcbfb2d5a091ba5ef3272ed8092eb0eff8b7ad979a82
# BUILD_DATE=20220922
# BUILD_TAG=2022-09-22
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-22
begin = 2022-09-22 12:02:23.734647746+00:00
start-sync_0 = 12:04:27
start-zstd = 12:06:12
start-sync_1 = 12:08:56
end-sync_1 = 12:09:10
end = 2022-09-22 12:09:10.244968328+00:00

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
ldd = 'ldd (Debian GLIBC 2.34-4) 2.34'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
