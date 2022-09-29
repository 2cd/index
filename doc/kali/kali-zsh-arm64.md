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
tag = ["zsh", "2022-09-29"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_arm64_2022-09-29_12-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b4983b98d9902cf15ca8a33d54d5e069efc3d052a35da42cce731f70152136aa"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "795M"
tar_bytes = 832567296

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "147M"
zstd_bytes = 153656898

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220922"
previous_tag = "2022-09-22"
previous_file = "kali-zsh_arm64_2022-09-22_12-17-rootfs.tar.zst"
previous_sha256 = "b8cee2873f0a6ddfb82d9ee1426c642394a888d586c335e36bc6ac7602d17175"

current_version = "latest01"
current_date = "20220929"
old_file = "kali-zsh_arm64_2022-09-15_12-17-rootfs.tar.zst"
old_sha256 = "0f9238222ed293eda1addd15c442be1a123324b58ff9b0d61e9a4b4d896b7711"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-zsh_arm64_2022-09-29_12-17-rootfs.tar.zst
# SHA256SUM=b4983b98d9902cf15ca8a33d54d5e069efc3d052a35da42cce731f70152136aa
# BUILD_DATE=20220929
# BUILD_TAG=2022-09-29
# STATUS=completed
# VERSION=latest01
# END_TIME=12:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-29
begin = 2022-09-29 12:02:22.415383304+00:00
start-sync_0 = 12:13:08
start-zstd = 12:14:55
start-sync_1 = 12:17:09
end-sync_1 = 12:17:25
end = 2022-09-29 12:17:25.246169219+00:00

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
ldd = 'ldd (Debian GLIBC 2.34-4) 2.34'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
