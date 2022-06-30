# kali-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-armv7 \
    cake233/kali-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it kali-zsh-armv7 zsh
```

## kali-zsh-armv7.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2022-06-30"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_armhf_2022-06-30_12-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "065fcaf57840f1927a270820d417ee764ecbb8d781197ee27e9ddc1266f4a3ad"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "683M"
tar_bytes = 715373056

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "142M"
zstd_bytes = 148492321

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220623"
previous_tag = "2022-06-23"
previous_file = "kali-zsh_armhf_2022-06-23_12-17-rootfs.tar.zst"
previous_sha256 = "cd5b897bce50466e0e2ea11c3721ac6e62740c0374a576329affa1e6b57a463f"

current_version = "latest01"
current_date = "20220630"
old_file = "kali-zsh_armhf_2022-06-16_12-18-rootfs.tar.zst"
old_sha256 = "28314fcb5f538f19532cf05432414a11ec0a3fe7f0bb65e57f6f1a743bbdfecd"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2022-06-30_12-20-rootfs.tar.zst
# SHA256SUM=065fcaf57840f1927a270820d417ee764ecbb8d781197ee27e9ddc1266f4a3ad
# BUILD_DATE=20220630
# BUILD_TAG=2022-06-30
# STATUS=completed
# VERSION=latest01
# END_TIME=12:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-30
begin = 2022-06-30 12:02:30.591529576+00:00
start-sync_0 = 12:15:47
start-zstd = 12:17:33
start-sync_1 = 12:19:58
end-sync_1 = 12:20:12
end = 2022-06-30 12:20:12.760635560+00:00

[server]
repo = "cake233/kali-zsh-armv7"

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```
