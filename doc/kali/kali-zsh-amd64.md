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
tag = ["zsh", "2023-04-06"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2023-04-06_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "42398c2b42397666e8aef346e6bd0a1354ed2aa9fcca000fe77544eafa07842d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "774M"
tar_bytes = 811163136

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "150M"
zstd_bytes = 156958077

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230330"
previous_tag = "2023-03-30"
previous_file = "kali-zsh_amd64_2023-03-30_12-11-rootfs.tar.zst"
previous_sha256 = "38d81130900f0253b3177ea1ff95afd1719f266af957c2c79f26f3dcead6e134"

current_version = "latest01"
current_date = "20230406"
old_file = "kali-zsh_amd64_2023-03-23_12-09-rootfs.tar.zst"
old_sha256 = "9f0301bdf98e06881758047944a4d196eca8e58f8fcfe2bec27d81d7f95f8fbf"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2023-04-06_12-09-rootfs.tar.zst
# SHA256SUM=42398c2b42397666e8aef346e6bd0a1354ed2aa9fcca000fe77544eafa07842d
# BUILD_DATE=20230406
# BUILD_TAG=2023-04-06
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-06
begin = 2023-04-06 12:02:27.807305492+00:00
start-sync_0 = 12:04:37
start-zstd = 12:06:26
start-sync_1 = 12:09:12
end-sync_1 = 12:09:27
end = 2023-04-06 12:09:27.215560668+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
