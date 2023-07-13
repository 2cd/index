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
tag = ["zsh", "2023-07-13"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_arm64_2023-07-13_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b39c947c41660b1a8c4c5a92de67070716e81db4f058b8bbf398b70c0ddcb8e1"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "816M"
tar_bytes = 855201280

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "150M"
zstd_bytes = 156381374

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230706"
previous_tag = "2023-07-06"
previous_file = "kali-zsh_arm64_2023-07-06_12-19-rootfs.tar.zst"
previous_sha256 = "e0d9d56338c3aa996ef20cad1409c821e9cca2c451c1b2044846a0d57789dcfd"

current_version = "latest01"
current_date = "20230713"
old_file = "kali-zsh_arm64_2023-06-29_12-18-rootfs.tar.zst"
old_sha256 = "1e55b454a99a7879e2dcc66821295fdd2762ebddd367a5122476177c7fc23ac7"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-zsh_arm64_2023-07-13_12-18-rootfs.tar.zst
# SHA256SUM=b39c947c41660b1a8c4c5a92de67070716e81db4f058b8bbf398b70c0ddcb8e1
# BUILD_DATE=20230713
# BUILD_TAG=2023-07-13
# STATUS=completed
# VERSION=latest01
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-13
begin = 2023-07-13 12:02:30.044314503+00:00
start-sync_0 = 12:14:17
start-zstd = 12:16:04
start-sync_1 = 12:18:28
end-sync_1 = 12:18:44
end = 2023-07-13 12:18:44.318084022+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
