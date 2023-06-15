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
tag = ["zsh", "2023-06-15"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_arm64_2023-06-15_12-19.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "97e0590cbeda36700c5a90844f334c4d567406b6b903fcd5f60cd9d892919a16"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "816M"
tar_bytes = 854901760

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "149M"
zstd_bytes = 156016156

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230608"
previous_tag = "2023-06-08"
previous_file = "kali-zsh_arm64_2023-06-08_12-18-rootfs.tar.zst"
previous_sha256 = "4ad4436aa8aebfb68250db9b99818a17da24dce862d56957114113266be9a71e"

current_version = "latest01"
current_date = "20230615"
old_file = "kali-zsh_arm64_2023-06-01_12-18-rootfs.tar.zst"
old_sha256 = "be6610643271991a49847cda76d60814c9985810eadcb674939ac951b811357d"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-zsh_arm64_2023-06-15_12-19-rootfs.tar.zst
# SHA256SUM=97e0590cbeda36700c5a90844f334c4d567406b6b903fcd5f60cd9d892919a16
# BUILD_DATE=20230615
# BUILD_TAG=2023-06-15
# STATUS=completed
# VERSION=latest01
# END_TIME=12:19

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-15
begin = 2023-06-15 12:02:33.008899504+00:00
start-sync_0 = 12:14:20
start-zstd = 12:16:09
start-sync_1 = 12:18:46
end-sync_1 = 12:19:01
end = 2023-06-15 12:19:01.337480133+00:00

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
