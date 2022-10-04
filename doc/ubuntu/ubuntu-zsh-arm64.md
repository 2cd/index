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
tag = ["zsh", "2022-10-04", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_arm64_2022-10-04_00-23.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "184ba2b1cdf620b9db306fc6ebc78475c9a2518729106705b1ed15b89c0e14e0"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "716M"
tar_bytes = 750500864

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "131M"
zstd_bytes = 137110260

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220927"
previous_tag = "2022-09-27"
previous_file = "ubuntu-zsh_arm64_2022-09-27_00-23-rootfs.tar.zst"
previous_sha256 = "390bd07951a9dbdbe8e0a02f961222839f42b54ab5aa187ca0872ac4890b4cf7"

current_version = "latest02"
current_date = "20221004"
old_file = "ubuntu-zsh_arm64_2022-09-20_00-18-rootfs.tar.zst"
old_sha256 = "2c9509c8739f4ae996d5dda2fa0c33d871803dbafea0cef0ac5dce992aa397b9"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-zsh_arm64_2022-10-04_00-23-rootfs.tar.zst
# SHA256SUM=184ba2b1cdf620b9db306fc6ebc78475c9a2518729106705b1ed15b89c0e14e0
# BUILD_DATE=20221004
# BUILD_TAG=2022-10-04
# STATUS=completed
# VERSION=latest02
# END_TIME=00:23

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-04
begin = 2022-10-04 00:02:28.971454614+00:00
start-sync_0 = 00:18:57
start-zstd = 00:20:48
start-sync_1 = 00:23:13
end-sync_1 = 00:23:31
end = 2022-10-04 00:23:31.048874200+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu3) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
