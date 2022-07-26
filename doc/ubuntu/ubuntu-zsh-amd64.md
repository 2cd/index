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
tag = ["zsh", "2022-07-26", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_amd64_2022-07-26_00-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e0b07520b91e3375cd856fde56b7ef7cfc47e3098b70fe8b9ed9c737f76d4007"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "687M"
tar_bytes = 720162816

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "133M"
zstd_bytes = 138744652

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220712"
previous_tag = "2022-07-12"
previous_file = "ubuntu-zsh_amd64_2022-07-12_00-08-rootfs.tar.zst"
previous_sha256 = "96ed616bad14622538dba9b61f1281796e103de2a7012d04c1403fb3ab9b8c60"

current_version = "latest01"
current_date = "20220726"
old_file = "ubuntu-zsh_amd64_2022-07-05_00-08-rootfs.tar.zst"
old_sha256 = "567356a44e6efe9f367e0e6f6ce727004e57eb4e546ad4292b039f6e061a2df2"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-zsh_amd64_2022-07-26_00-08-rootfs.tar.zst
# SHA256SUM=e0b07520b91e3375cd856fde56b7ef7cfc47e3098b70fe8b9ed9c737f76d4007
# BUILD_DATE=20220726
# BUILD_TAG=2022-07-26
# STATUS=completed
# VERSION=latest01
# END_TIME=00:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-26
begin = 2022-07-26 00:02:27.612882963+00:00
start-sync_0 = 00:04:32
start-zstd = 00:06:13
start-sync_1 = 00:08:26
end-sync_1 = 00:08:40
end = 2022-07-26 00:08:40.152797941+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'
```
