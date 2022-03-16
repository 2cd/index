# arch-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-armv7 \
    cake233/arch-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it arch-zsh-armv7 zsh
```

## arch-zsh-armv7.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2022-03-16"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "arch-zsh_armhf_2022-03-16_00-29.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "e90db169dc466c8623035f9006e64a69dbdd1341f11873d74fbabfea893c7b0f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "858M"
tar_bytes = 899021824

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "210M"
zstd_bytes = 219349384

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220309"
previous_tag = "2022-03-09"
previous_file = "arch-zsh_armhf_2022-03-09_00-34-rootfs.tar.zst"
previous_sha256 = "e0a458c197c272166eae68e9b35a50a8dfe985bfddae2aa00f6f04ed3ab2373f"

current_version = "latest02"
current_date = "20220316"
old_file = "arch-zsh_armhf_2022-03-02_00-39-rootfs.tar.zst"
old_sha256 = "b94266f935cfd6a1c1a7c79846e9189cd7f70b50ca3b7dc75d34fca58728b2f6"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-zsh_armhf_2022-03-16_00-29-rootfs.tar.zst
# SHA256SUM=e90db169dc466c8623035f9006e64a69dbdd1341f11873d74fbabfea893c7b0f
# BUILD_DATE=20220316
# BUILD_TAG=2022-03-16
# STATUS=completed
# VERSION=latest02
# END_TIME=00:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-16
begin = 2022-03-16 00:06:52.565011052+00:00
start-sync_0 = 00:24:02
start-zstd = 00:25:39
start-sync_1 = 00:28:57
end-sync_1 = 00:29:14
end = 2022-03-16 00:29:14.861402442+00:00

[server]
repo = "cake233/arch-zsh-armv7"

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
zsh = 'zsh 5.8.1 (armv7l-unknown-linux-gnueabihf)'
```
