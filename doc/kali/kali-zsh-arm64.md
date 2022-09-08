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
tag = ["zsh", "2022-09-08"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_arm64_2022-09-08_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "690922a1f6fc86909e52655de5ee5c66ab26c11cbacdae08abcd857b575191fc"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "787M"
tar_bytes = 824641536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "147M"
zstd_bytes = 154013414

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220901"
previous_tag = "2022-09-01"
previous_file = "kali-zsh_arm64_2022-09-01_12-17-rootfs.tar.zst"
previous_sha256 = "a8ce780ff25a5e30a3817dd024d0b7037835dab3e0933650ad58c7892746faf0"

current_version = "latest02"
current_date = "20220908"
old_file = "kali-zsh_arm64_2022-08-25_12-17-rootfs.tar.zst"
old_sha256 = "2ed6f251fddd90a6596901aa85ad7721cef9eaf9e0972f93bef73a862ba71909"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-zsh_arm64_2022-09-08_12-18-rootfs.tar.zst
# SHA256SUM=690922a1f6fc86909e52655de5ee5c66ab26c11cbacdae08abcd857b575191fc
# BUILD_DATE=20220908
# BUILD_TAG=2022-09-08
# STATUS=completed
# VERSION=latest02
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-08
begin = 2022-09-08 12:02:21.319915007+00:00
start-sync_0 = 12:14:24
start-zstd = 12:16:10
start-sync_1 = 12:18:31
end-sync_1 = 12:18:44
end = 2022-09-08 12:18:44.480409327+00:00

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
ldd = 'ldd (Debian GLIBC 2.34-4) 2.34'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
