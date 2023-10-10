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
tag = ["zsh", "2023-10-10"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_amd64_2023-10-10_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e541d260cb133172f2caea0c75f15944d84817c9d4d63330d024e50e5412af7d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.4G"
tar_bytes = 1417804800

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "240M"
zstd_bytes = 251298989

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231003"
previous_tag = "2023-10-03"
previous_file = "fedora-zsh_amd64_2023-10-03_12-11-rootfs.tar.zst"
previous_sha256 = "12840a94b3f4ce1560e848ec65ba36379abb037cf7269cb9b6a0435b71f61666"

current_version = "latest02"
current_date = "20231010"
old_file = "fedora-zsh_amd64_2023-09-26_12-12-rootfs.tar.zst"
old_sha256 = "676b40d0d8c78cbd6b5eb0565185c38921e75084fd72234a6b6f1b15103e71d1"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2023-10-10_12-12-rootfs.tar.zst
# SHA256SUM=e541d260cb133172f2caea0c75f15944d84817c9d4d63330d024e50e5412af7d
# BUILD_DATE=20231010
# BUILD_TAG=2023-10-10
# STATUS=completed
# VERSION=latest02
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-10
begin = 2023-10-10 12:02:38.980792592+00:00
start-sync_0 = 12:05:05
start-zstd = 12:07:14
start-sync_1 = 12:11:41
end-sync_1 = 12:12:06
end = 2023-10-10 12:12:06.316522095+00:00

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
ldd = 'ldd (GNU libc) 2.38.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'
```
