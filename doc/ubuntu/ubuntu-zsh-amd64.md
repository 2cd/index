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
tag = ["zsh", "2022-10-18", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_amd64_2022-10-18_00-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "940a63a129136df686cb61d29a140f895de1972af39c391fb17ab4a064ff25be"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "689M"
tar_bytes = 722193408

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "133M"
zstd_bytes = 139017661

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221011"
previous_tag = "2022-10-11"
previous_file = "ubuntu-zsh_amd64_2022-10-11_00-09-rootfs.tar.zst"
previous_sha256 = "26e7cd3294118eb5a33d034ba2096a009ebeda09ad61fe5fd550f1cab1aaa2e8"

current_version = "latest02"
current_date = "20221018"
old_file = "ubuntu-zsh_amd64_2022-10-04_00-08-rootfs.tar.zst"
old_sha256 = "655fc8ea20732c1520f6a74286cbe3d6dee7457d849e6e153b054d6f735aa516"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-zsh_amd64_2022-10-18_00-09-rootfs.tar.zst
# SHA256SUM=940a63a129136df686cb61d29a140f895de1972af39c391fb17ab4a064ff25be
# BUILD_DATE=20221018
# BUILD_TAG=2022-10-18
# STATUS=completed
# VERSION=latest02
# END_TIME=00:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-18
begin = 2022-10-18 00:02:27.871736769+00:00
start-sync_0 = 00:04:57
start-zstd = 00:06:51
start-sync_1 = 00:09:26
end-sync_1 = 00:09:45
end = 2022-10-18 00:09:45.774592625+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'
```
