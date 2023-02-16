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
tag = ["zsh", "2023-02-16"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_arm64_2023-02-16_12-23.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5416ff51bba0531da8b1560cffa676d721578a7dfde8c4e5d33710d81cf47232"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "815M"
tar_bytes = 853833728

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "149M"
zstd_bytes = 156045194

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230209"
previous_tag = "2023-02-09"
previous_file = "kali-zsh_arm64_2023-02-09_12-20-rootfs.tar.zst"
previous_sha256 = "d76b54357f7ba899d3c0c9f57f888a03e5c43c2befcff6167b5edd1421323c76"

current_version = "latest01"
current_date = "20230216"
old_file = "kali-zsh_arm64_2023-02-02_12-23-rootfs.tar.zst"
old_sha256 = "5c0e010fe4fae1a8067845fc31d180d528ecf166adc0ace60b21831e99f602e6"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-zsh_arm64_2023-02-16_12-23-rootfs.tar.zst
# SHA256SUM=5416ff51bba0531da8b1560cffa676d721578a7dfde8c4e5d33710d81cf47232
# BUILD_DATE=20230216
# BUILD_TAG=2023-02-16
# STATUS=completed
# VERSION=latest01
# END_TIME=12:23

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-16
begin = 2023-02-16 12:02:27.800430908+00:00
start-sync_0 = 12:18:41
start-zstd = 12:20:40
start-sync_1 = 12:23:35
end-sync_1 = 12:23:53
end = 2023-02-16 12:23:53.329238242+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
