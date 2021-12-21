# ubuntu-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-zsh-arm64 \
    cake233/ubuntu-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it ubuntu-zsh-arm64 zsh
```

## ubuntu-zsh-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2021-12-21", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "ubuntu-zsh_arm64_2021-12-21_00-18.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "948ac48fa91312b862f3ef7ae82ff817d2947f5c62173c16ed13e749727e9373"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "621M"
tar_bytes = 651101184

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "111M"
zstd_bytes = 115802874

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211214"
previous_tag = "2021-12-14"
previous_file = "ubuntu-zsh_arm64_2021-12-14_00-20-rootfs.tar.zst"
previous_sha256 = "ef3099c38c9161e9378f4315f68842911efd6a348e2f303414d8c7081011563c"

current_version = "latest02"
current_date = "20211221"
old_file = "ubuntu-zsh_arm64_2021-12-07_00-22-rootfs.tar.zst"
old_sha256 = "22dca6b25452c415a08ca8199dbe949a7df457548d70c4aa38e3fc81ea91c4a8"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-zsh_arm64_2021-12-21_00-18-rootfs.tar.zst
# SHA256SUM=948ac48fa91312b862f3ef7ae82ff817d2947f5c62173c16ed13e749727e9373
# BUILD_DATE=20211221
# BUILD_TAG=2021-12-21
# STATUS=completed
# VERSION=latest02
# END_TIME=00:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-21
begin = 2021-12-21 00:02:25.811709380+00:00
start-sync_0 = 00:14:30
start-zstd = 00:16:16
start-sync_1 = 00:18:40
end-sync_1 = 00:18:53
end = 2021-12-21 00:18:53.265685298+00:00

[server]
repo = "cake233/ubuntu-zsh-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.34-0ubuntu3) 2.34'
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'
```
