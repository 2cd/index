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
tag = ["zsh", "2023-10-24"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_amd64_2023-10-24_12-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "91fb601b8fb5b87eb019a10157995a0b9f2794d9c60d39705af5cd680858c6c2"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.4G"
tar_bytes = 1419368448

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "241M"
zstd_bytes = 251786193

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231017"
previous_tag = "2023-10-17"
previous_file = "fedora-zsh_amd64_2023-10-17_12-13-rootfs.tar.zst"
previous_sha256 = "1abae7e28eeb6777f73cab8c8e27b1e035b76874869520e4b3514452bfbd25cd"

current_version = "latest02"
current_date = "20231024"
old_file = "fedora-zsh_amd64_2023-10-10_12-12-rootfs.tar.zst"
old_sha256 = "e541d260cb133172f2caea0c75f15944d84817c9d4d63330d024e50e5412af7d"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2023-10-24_12-13-rootfs.tar.zst
# SHA256SUM=91fb601b8fb5b87eb019a10157995a0b9f2794d9c60d39705af5cd680858c6c2
# BUILD_DATE=20231024
# BUILD_TAG=2023-10-24
# STATUS=completed
# VERSION=latest02
# END_TIME=12:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-24
begin = 2023-10-24 12:02:38.548279337+00:00
start-sync_0 = 12:05:09
start-zstd = 12:07:31
start-sync_1 = 12:12:56
end-sync_1 = 12:13:26
end = 2023-10-24 12:13:26.124816330+00:00

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
