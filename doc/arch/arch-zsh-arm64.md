# arch-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-arm64 \
    cake233/arch-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it arch-zsh-arm64 zsh
```

## arch-zsh-arm64.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2022-03-02"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "arch-zsh_arm64_2022-03-02_00-30.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "344eeb460a13e1d08b02e7e5d2ca5cfe83522c818ce4ed0d6b293da567399312"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "955M"
tar_bytes = 1000504320

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "224M"
zstd_bytes = 233912713

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220223"
previous_tag = "2022-02-23"
previous_file = "arch-zsh_arm64_2022-02-23_00-24-rootfs.tar.zst"
previous_sha256 = "3b307a1ff365f31825ab40b6c0700561f52761adf19e047adfaef571029ea023"

current_version = "latest01"
current_date = "20220302"
old_file = "arch-zsh_arm64_2022-02-16_00-30-rootfs.tar.zst"
old_sha256 = "c6d6b35256e20e6eb59edb849c53cf7107f4d2c10c0acfeff8f63fa48f1f7789"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2022-03-02_00-30-rootfs.tar.zst
# SHA256SUM=344eeb460a13e1d08b02e7e5d2ca5cfe83522c818ce4ed0d6b293da567399312
# BUILD_DATE=20220302
# BUILD_TAG=2022-03-02
# STATUS=completed
# VERSION=latest01
# END_TIME=00:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-02
begin = 2022-03-02 00:11:10.764396185+00:00
start-sync_0 = 00:24:25
start-zstd = 00:26:25
start-sync_1 = 00:30:14
end-sync_1 = 00:30:34
end = 2022-03-02 00:30:34.628651184+00:00

[server]
repo = "cake233/arch-zsh-arm64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'
```
