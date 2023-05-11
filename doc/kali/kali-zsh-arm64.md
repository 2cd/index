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
tag = ["zsh", "2023-05-11"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_arm64_2023-05-11_12-21.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "717c8b65dab87285401cbff1992077f15e79efeaf5965025d1f1748e12dafa00"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "816M"
tar_bytes = 854976000

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "149M"
zstd_bytes = 156024499

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230504"
previous_tag = "2023-05-04"
previous_file = "kali-zsh_arm64_2023-05-04_12-19-rootfs.tar.zst"
previous_sha256 = "8b517154652f02389a610eee79a822f4ddab2a5949cbe2d11e012d1cc16ca0f0"

current_version = "latest02"
current_date = "20230511"
old_file = "kali-zsh_arm64_2023-04-27_12-18-rootfs.tar.zst"
old_sha256 = "22debf324826392b997b055c5404fbd69450a7a855287011c7c549d508ec14c1"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-zsh_arm64_2023-05-11_12-21-rootfs.tar.zst
# SHA256SUM=717c8b65dab87285401cbff1992077f15e79efeaf5965025d1f1748e12dafa00
# BUILD_DATE=20230511
# BUILD_TAG=2023-05-11
# STATUS=completed
# VERSION=latest02
# END_TIME=12:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-11
begin = 2023-05-11 12:02:32.893685853+00:00
start-sync_0 = 12:16:36
start-zstd = 12:18:32
start-sync_1 = 12:21:35
end-sync_1 = 12:21:53
end = 2023-05-11 12:21:53.752695075+00:00

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
