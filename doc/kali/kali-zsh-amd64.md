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
tag = ["zsh", "2022-10-06"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2022-10-06_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "af6b6e870b91d53a48728661b8f35e1ae242c6e2e0a72ba867818da8dbde4384"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "757M"
tar_bytes = 793747456

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "148M"
zstd_bytes = 154339813

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220929"
previous_tag = "2022-09-29"
previous_file = "kali-zsh_amd64_2022-09-29_12-08-rootfs.tar.zst"
previous_sha256 = "84b22ec8a5f5f9adaf50824584044f3b998dbcf48b34c7afc2c9ca85f86fdd8d"

current_version = "latest01"
current_date = "20221006"
old_file = "kali-zsh_amd64_2022-09-22_12-09-rootfs.tar.zst"
old_sha256 = "185b18f73b9687bbca80dcbfb2d5a091ba5ef3272ed8092eb0eff8b7ad979a82"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2022-10-06_12-11-rootfs.tar.zst
# SHA256SUM=af6b6e870b91d53a48728661b8f35e1ae242c6e2e0a72ba867818da8dbde4384
# BUILD_DATE=20221006
# BUILD_TAG=2022-10-06
# STATUS=completed
# VERSION=latest01
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-06
begin = 2022-10-06 12:02:37.683383039+00:00
start-sync_0 = 12:05:17
start-zstd = 12:07:18
start-sync_1 = 12:10:38
end-sync_1 = 12:11:00
end = 2022-10-06 12:11:00.783757353+00:00

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
