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
tag = ["zsh", "2022-07-19", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_arm64_2022-07-19_00-19.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "88ee0b8ea9404f9c97c57faaed476bdea79e60654957c39d7b4c5248b35a0b9b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "686M"
tar_bytes = 719261696

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "131M"
zstd_bytes = 137273974

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220712"
previous_tag = "2022-07-12"
previous_file = "ubuntu-zsh_arm64_2022-07-12_00-20-rootfs.tar.zst"
previous_sha256 = "694a0364818fcac12ca13baddf3276adfd8517530377d54855533546a757e0ec"

current_version = "latest01"
current_date = "20220719"
old_file = "ubuntu-zsh_arm64_2022-07-05_00-17-rootfs.tar.zst"
old_sha256 = "fce9f73c5e855884f33d9ee2c0edca2292385b6f0d4acfce77a1193e8478d3a2"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-zsh_arm64_2022-07-19_00-19-rootfs.tar.zst
# SHA256SUM=88ee0b8ea9404f9c97c57faaed476bdea79e60654957c39d7b4c5248b35a0b9b
# BUILD_DATE=20220719
# BUILD_TAG=2022-07-19
# STATUS=completed
# VERSION=latest01
# END_TIME=00:19

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-19
begin = 2022-07-19 00:02:26.902621129+00:00
start-sync_0 = 00:15:19
start-zstd = 00:17:01
start-sync_1 = 00:19:10
end-sync_1 = 00:19:23
end = 2022-07-19 00:19:23.969619415+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
