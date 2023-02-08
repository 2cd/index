# arch-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-amd64 \
    cake233/arch-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it arch-zsh-amd64 zsh
```

## arch-zsh-amd64.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2023-02-08"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_amd64_2023-02-08_00-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2425b7084a993faf274dca014c892f5acfe88b249c980972bf25e8c63380041f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1109259776

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "267M"
zstd_bytes = 279152801

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230201"
previous_tag = "2023-02-01"
previous_file = "arch-zsh_amd64_2023-02-01_00-18-rootfs.tar.zst"
previous_sha256 = "19e021b1b47b10299157b07c5105e861c9cc46edcf97e781fc818d2b2ceb405a"

current_version = "latest02"
current_date = "20230208"
old_file = "arch-zsh_amd64_2023-01-25_00-17-rootfs.tar.zst"
old_sha256 = "cdaa74f68600bc86f0bfe955460867ca239fd5328dcb2727e3b57e692d655a58"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-zsh_amd64_2023-02-08_00-17-rootfs.tar.zst
# SHA256SUM=2425b7084a993faf274dca014c892f5acfe88b249c980972bf25e8c63380041f
# BUILD_DATE=20230208
# BUILD_TAG=2023-02-08
# STATUS=completed
# VERSION=latest02
# END_TIME=00:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-08
begin = 2023-02-08 00:07:58.903472316+00:00
start-sync_0 = 00:11:22
start-zstd = 00:12:55
start-sync_1 = 00:16:50
end-sync_1 = 00:17:16
end = 2023-02-08 00:17:16.601531272+00:00

[server]
repo = "cake233/arch-zsh-amd64"

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
