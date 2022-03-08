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
tag = ["zsh", "2022-03-08", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "ubuntu-zsh_arm64_2022-03-08_00-16.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "453c576f92625430fde1cb2311982915c24cd4aead1f4092db808b8c3ec55429"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "623M"
tar_bytes = 653128704

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "112M"
zstd_bytes = 117290196

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220301"
previous_tag = "2022-03-01"
previous_file = "ubuntu-zsh_arm64_2022-03-01_00-20-rootfs.tar.zst"
previous_sha256 = "2ace65017c10a9939f24d6214aa9b2864fbb97c986370f62c894b7bcf740193b"

current_version = "latest01"
current_date = "20220308"
old_file = "ubuntu-zsh_arm64_2022-02-22_00-18-rootfs.tar.zst"
old_sha256 = "7b5550fb411cf06f3e852062b1e38d2dfc3f78a53e98e1af4b7b8b159c0f584b"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-zsh_arm64_2022-03-08_00-16-rootfs.tar.zst
# SHA256SUM=453c576f92625430fde1cb2311982915c24cd4aead1f4092db808b8c3ec55429
# BUILD_DATE=20220308
# BUILD_TAG=2022-03-08
# STATUS=completed
# VERSION=latest01
# END_TIME=00:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-08
begin = 2022-03-08 00:02:27.633374610+00:00
start-sync_0 = 00:12:16
start-zstd = 00:13:57
start-sync_1 = 00:16:04
end-sync_1 = 00:16:15
end = 2022-03-08 00:16:15.106129468+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu1) 2.35'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'
```
