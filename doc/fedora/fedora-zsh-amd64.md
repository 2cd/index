# fedora-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name fedora-zsh-amd64 \
    cake233/fedora-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it fedora-zsh-amd64 zsh
```

## fedora-zsh-amd64.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2023-01-17"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_amd64_2023-01-17_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "414e701195dd404eb19e7cf8d87f61458b4ea5f8d6efa6269bfcea2ef76dedad"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1322420736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "222M"
zstd_bytes = 232341602

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230110"
previous_tag = "2023-01-10"
previous_file = "fedora-zsh_amd64_2023-01-10_12-13-rootfs.tar.zst"
previous_sha256 = "1196607abdbc63e1dba37a38f011a99c72b83e8c5f614a68c822445d2099785b"

current_version = "latest02"
current_date = "20230117"
old_file = "fedora-zsh_amd64_2023-01-03_12-10-rootfs.tar.zst"
old_sha256 = "4ca687fe24ec0cbb45415ac42c14cdf5523525162e889c9df289aeb4cb37106e"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2023-01-17_12-12-rootfs.tar.zst
# SHA256SUM=414e701195dd404eb19e7cf8d87f61458b4ea5f8d6efa6269bfcea2ef76dedad
# BUILD_DATE=20230117
# BUILD_TAG=2023-01-17
# STATUS=completed
# VERSION=latest02
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-17
begin = 2023-01-17 12:02:25.652443137+00:00
start-sync_0 = 12:05:11
start-zstd = 12:07:19
start-sync_1 = 12:11:41
end-sync_1 = 12:12:00
end = 2023-01-17 12:12:00.197220843+00:00

[server]
repo = "cake233/fedora-zsh-amd64"

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'
```
