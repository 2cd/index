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
tag = ["zsh", "2022-03-15", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "ubuntu-zsh_arm64_2022-03-15_00-22.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "146ccaaf2c5e675c2f681bdeed373f10c83a5dabcd75e68346356b9dfba24070"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "623M"
tar_bytes = 653193728

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "112M"
zstd_bytes = 117328816

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220308"
previous_tag = "2022-03-08"
previous_file = "ubuntu-zsh_arm64_2022-03-08_00-16-rootfs.tar.zst"
previous_sha256 = "453c576f92625430fde1cb2311982915c24cd4aead1f4092db808b8c3ec55429"

current_version = "latest02"
current_date = "20220315"
old_file = "ubuntu-zsh_arm64_2022-03-01_00-20-rootfs.tar.zst"
old_sha256 = "2ace65017c10a9939f24d6214aa9b2864fbb97c986370f62c894b7bcf740193b"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-zsh_arm64_2022-03-15_00-22-rootfs.tar.zst
# SHA256SUM=146ccaaf2c5e675c2f681bdeed373f10c83a5dabcd75e68346356b9dfba24070
# BUILD_DATE=20220315
# BUILD_TAG=2022-03-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-15
begin = 2022-03-15 00:02:24.435018108+00:00
start-sync_0 = 00:17:38
start-zstd = 00:19:27
start-sync_1 = 00:22:05
end-sync_1 = 00:22:17
end = 2022-03-15 00:22:17.638854296+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'
```
