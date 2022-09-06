# ubuntu-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-zsh-amd64 \
    cake233/ubuntu-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it ubuntu-zsh-amd64 zsh
```

## ubuntu-zsh-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2022-09-06", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_amd64_2022-09-06_00-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7e78dcfb9e04ae367ed9b459e76fb195267d7873a6e57d35de6db04f74596607"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "688M"
tar_bytes = 720919040

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "133M"
zstd_bytes = 138662711

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220823"
previous_tag = "2022-08-23"
previous_file = "ubuntu-zsh_amd64_2022-08-23_00-08-rootfs.tar.zst"
previous_sha256 = "6cb7fdcfe075b0c551410574cc94ee5832f213d5b8b618e6a5d4ff6bbfbe068e"

current_version = "latest02"
current_date = "20220906"
old_file = "ubuntu-zsh_amd64_2022-08-16_00-08-rootfs.tar.zst"
old_sha256 = "38f5cffadeccc640ea6288d431fcf1dfbc3f6794d47e2b990f8696db88d97b6c"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-zsh_amd64_2022-09-06_00-09-rootfs.tar.zst
# SHA256SUM=7e78dcfb9e04ae367ed9b459e76fb195267d7873a6e57d35de6db04f74596607
# BUILD_DATE=20220906
# BUILD_TAG=2022-09-06
# STATUS=completed
# VERSION=latest02
# END_TIME=00:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-06
begin = 2022-09-06 00:02:22.185075032+00:00
start-sync_0 = 00:04:41
start-zstd = 00:06:30
start-sync_1 = 00:09:03
end-sync_1 = 00:09:19
end = 2022-09-06 00:09:19.501831538+00:00

[server]
repo = "cake233/ubuntu-zsh-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu2) 2.36'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'
```
