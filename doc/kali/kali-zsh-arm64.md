# kali-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-arm64 \
    cake233/kali-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it kali-zsh-arm64 zsh
```

## kali-zsh-arm64.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2023-06-01"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_arm64_2023-06-01_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "be6610643271991a49847cda76d60814c9985810eadcb674939ac951b811357d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "816M"
tar_bytes = 855045120

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "149M"
zstd_bytes = 156095103

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230525"
previous_tag = "2023-05-25"
previous_file = "kali-zsh_arm64_2023-05-25_12-21-rootfs.tar.zst"
previous_sha256 = "ce17b9f1816947c2e2575b74b1d61ce8da818692ab2718fb0fe72c73d855b171"

current_version = "latest01"
current_date = "20230601"
old_file = "kali-zsh_arm64_2023-05-18_12-25-rootfs.tar.zst"
old_sha256 = "dfbd248dfe54e1ecb84df6da2ddbadad110466e51a881d30b685a1b466823f45"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-zsh_arm64_2023-06-01_12-18-rootfs.tar.zst
# SHA256SUM=be6610643271991a49847cda76d60814c9985810eadcb674939ac951b811357d
# BUILD_DATE=20230601
# BUILD_TAG=2023-06-01
# STATUS=completed
# VERSION=latest01
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-01
begin = 2023-06-01 12:02:41.018287044+00:00
start-sync_0 = 12:14:20
start-zstd = 12:16:03
start-sync_1 = 12:18:37
end-sync_1 = 12:18:51
end = 2023-06-01 12:18:51.208236382+00:00

[server]
repo = "cake233/kali-zsh-arm64"

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
