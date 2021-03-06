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
tag = ["zsh", "2022-07-21"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2022-07-21_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "15d168e409831b1f2b8ed98be34c6ea3db9073a2c6916f8bcc11c074725a361d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "752M"
tar_bytes = 788090880

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "147M"
zstd_bytes = 153144010

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220714"
previous_tag = "2022-07-14"
previous_file = "kali-zsh_amd64_2022-07-14_12-10-rootfs.tar.zst"
previous_sha256 = "dd071352e5c5102f26c9f5ff1a0e07f2ae22e389318a331f40a137255c82278b"

current_version = "latest02"
current_date = "20220721"
old_file = "kali-zsh_amd64_2022-07-07_12-09-rootfs.tar.zst"
old_sha256 = "0f6e1906b1e954a5fb722ab78b970fe967b9c7bdba2f9cb2cefb3cb58eb9db5e"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2022-07-21_12-10-rootfs.tar.zst
# SHA256SUM=15d168e409831b1f2b8ed98be34c6ea3db9073a2c6916f8bcc11c074725a361d
# BUILD_DATE=20220721
# BUILD_TAG=2022-07-21
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-21
begin = 2022-07-21 12:02:28.139573529+00:00
start-sync_0 = 12:05:35
start-zstd = 12:07:31
start-sync_1 = 12:10:41
end-sync_1 = 12:10:58
end = 2022-07-21 12:10:58.862362133+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
