# debian-zsh-386

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-386 \
    cake233/debian-zsh-386
```

## How to exec shell?

```sh
docker exec -it debian-zsh-386 zsh
```

## debian-zsh-386.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2022-01-26"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
x11_or_wayland = false

[file]
name = "debian-zsh_i386_2022-01-26_12-19.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "885b8b8c8c0faf4bdc850a37158b2558d5fc237abc9b275923d90b18a86b9858"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "740M"
tar_bytes = 775683072

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "145M"
zstd_bytes = 151737048

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220119"
previous_tag = "2022-01-19"
previous_file = "debian-zsh_i386_2022-01-19_12-22-rootfs.tar.zst"
previous_sha256 = "fbbd747e40a53cc52837534618dcc62ac802c03b8b963ad5647c561810a6fac5"

current_version = "latest02"
current_date = "20220126"
old_file = "debian-zsh_i386_2022-01-12_12-21-rootfs.tar.zst"
old_sha256 = "b11ce3b627d8a016de37bca75dfdb2a2b69e30a222645ee2afb5cf14a944a43d"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-zsh_i386_2022-01-26_12-19-rootfs.tar.zst
# SHA256SUM=885b8b8c8c0faf4bdc850a37158b2558d5fc237abc9b275923d90b18a86b9858
# BUILD_DATE=20220126
# BUILD_TAG=2022-01-26
# STATUS=completed
# VERSION=latest02
# END_TIME=12:19

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-26
begin = 2022-01-26 12:02:24.547903646+00:00
start-sync_0 = 12:14:57
start-zstd = 12:16:46
start-sync_1 = 12:19:23
end-sync_1 = 12:19:38
end = 2022-01-26 12:19:38.485900026+00:00

[server]
repo = "cake233/debian-zsh-386"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (Debian GLIBC 2.33-4) 2.33'
zsh = 'zsh 5.8 (i686-debian-linux-gnu)'
```
