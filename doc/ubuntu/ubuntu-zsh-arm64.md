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
tag = ["zsh", "2023-11-28", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_arm64_2023-11-28_00-22.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7f2949eb921cf83e67f48fb11e63cd2f9ae4e66329c015e343ee50cb445e8be5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "803M"
tar_bytes = 841495552

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "151M"
zstd_bytes = 158276083

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231121"
previous_tag = "2023-11-21"
previous_file = "ubuntu-zsh_arm64_2023-11-21_00-23-rootfs.tar.zst"
previous_sha256 = "56743afceb8f982f3803799f3288eea5afaeeffff805897dd5aa438f4da35d9c"

current_version = "latest01"
current_date = "20231128"
old_file = "ubuntu-zsh_arm64_2023-11-14_00-22-rootfs.tar.zst"
old_sha256 = "bb403344816cbe00a2f3c07446864a6dd33c847eb0177aab35e7beef8b960618"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-zsh_arm64_2023-11-28_00-22-rootfs.tar.zst
# SHA256SUM=7f2949eb921cf83e67f48fb11e63cd2f9ae4e66329c015e343ee50cb445e8be5
# BUILD_DATE=20231128
# BUILD_TAG=2023-11-28
# STATUS=completed
# VERSION=latest01
# END_TIME=00:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-28
begin = 2023-11-28 00:02:27.486908589+00:00
start-sync_0 = 00:19:10
start-zstd = 00:20:45
start-sync_1 = 00:22:46
end-sync_1 = 00:22:57
end = 2023-11-28 00:22:57.733601331+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu6) 2.38'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
