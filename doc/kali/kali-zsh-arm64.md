# kali-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-arm64 \
    cake233/kali-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it kali-zsh-arm64 zsh
```

## kali-zsh-arm64.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2023-01-05"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_arm64_2023-01-05_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b8a052696283d12bfa464c60f49c8d63f11540c08c7d58037dfa24d5ef5ee016"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "806M"
tar_bytes = 844206080

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "147M"
zstd_bytes = 153569159

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221229"
previous_tag = "2022-12-29"
previous_file = "kali-zsh_arm64_2022-12-29_12-17-rootfs.tar.zst"
previous_sha256 = "430af53e90949bc87fbca8f062bd2720850dacbb9bc9ee83f3e7e623976fd9a3"

current_version = "latest01"
current_date = "20230105"
old_file = "kali-zsh_arm64_2022-12-22_12-18-rootfs.tar.zst"
old_sha256 = "92cbbca61fed566245d4d2ccbea4f2636b388841fd37d0bb2c5b90a86893f76c"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-zsh_arm64_2023-01-05_12-18-rootfs.tar.zst
# SHA256SUM=b8a052696283d12bfa464c60f49c8d63f11540c08c7d58037dfa24d5ef5ee016
# BUILD_DATE=20230105
# BUILD_TAG=2023-01-05
# STATUS=completed
# VERSION=latest01
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-05
begin = 2023-01-05 12:02:25.817404235+00:00
start-sync_0 = 12:14:13
start-zstd = 12:15:58
start-sync_1 = 12:18:32
end-sync_1 = 12:18:47
end = 2023-01-05 12:18:47.098001833+00:00

[server]
repo = "cake233/kali-zsh-arm64"

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
ldd = 'ldd (Debian GLIBC 2.36-6) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
