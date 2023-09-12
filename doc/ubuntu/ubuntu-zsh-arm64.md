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
tag = ["zsh", "2023-09-12", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_arm64_2023-09-12_00-22.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "79423376e756c356417fd69d5ad67bbee7a531075f4d6f8e4f708cb3466c85bd"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "806M"
tar_bytes = 845108736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "152M"
zstd_bytes = 159319764

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230905"
previous_tag = "2023-09-05"
previous_file = "ubuntu-zsh_arm64_2023-09-05_00-22-rootfs.tar.zst"
previous_sha256 = "f621ccd859bb2e46863acc3e1c4433b927533917434b852a5895df4c2bc6bf3c"

current_version = "latest02"
current_date = "20230912"
old_file = "ubuntu-zsh_arm64_2023-08-29_00-25-rootfs.tar.zst"
old_sha256 = "0ebb08ee07e221023b82eb4fdc3771a9eb84ebb2b697ab28cfd23c5f73c434d5"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-zsh_arm64_2023-09-12_00-22-rootfs.tar.zst
# SHA256SUM=79423376e756c356417fd69d5ad67bbee7a531075f4d6f8e4f708cb3466c85bd
# BUILD_DATE=20230912
# BUILD_TAG=2023-09-12
# STATUS=completed
# VERSION=latest02
# END_TIME=00:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-12
begin = 2023-09-12 00:02:33.214099968+00:00
start-sync_0 = 00:17:58
start-zstd = 00:19:41
start-sync_1 = 00:22:14
end-sync_1 = 00:22:31
end = 2023-09-12 00:22:31.756408852+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu4) 2.38'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
