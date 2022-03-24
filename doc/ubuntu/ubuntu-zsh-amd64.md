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
tag = ["zsh", "2022-03-24", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "ubuntu-zsh_amd64_2022-03-24_18-45.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "1ffd683533362e9f5ad3b00c2d5a707f2d01a1c6c6d145c986e4bb784bca51ea"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "634M"
tar_bytes = 663980544

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "114M"
zstd_bytes = 118542601

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220322"
previous_tag = "2022-03-22"
previous_file = "ubuntu-zsh_amd64_2022-03-22_00-09-rootfs.tar.zst"
previous_sha256 = "f30c9e27efaeec69bd31afc824763caa00c8a6443409eb8a129b22d1b830760c"

current_version = "latest02"
current_date = "20220324"
old_file = "ubuntu-zsh_amd64_2022-03-15_00-08-rootfs.tar.zst"
old_sha256 = "d0af56210b45f2db03e4a101a2e83de24378fa13da8ed2cfe20cda581e9b4b1a"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-zsh_amd64_2022-03-24_18-45-rootfs.tar.zst
# SHA256SUM=1ffd683533362e9f5ad3b00c2d5a707f2d01a1c6c6d145c986e4bb784bca51ea
# BUILD_DATE=20220324
# BUILD_TAG=2022-03-24
# STATUS=completed
# VERSION=latest02
# END_TIME=18:45

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-24
begin = 2022-03-24 18:39:40.514663492+00:00
start-sync_0 = 18:41:17
start-zstd = 18:42:59
start-sync_1 = 18:45:25
end-sync_1 = 18:45:37
end = 2022-03-24 18:45:37.827617668+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.8.1 (x86_64-ubuntu-linux-gnu)'
```
