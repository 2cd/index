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
tag = ["zsh", "2024-02-27", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_arm64_2024-02-27_00-43.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ed39b927b914f5d07b8a52d2be41d9d095d91dc39b5e339aba2f5086bd033001"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "772M"
tar_bytes = 809490432

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "143M"
zstd_bytes = 149368164

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231128"
previous_tag = "2023-11-28"
previous_file = "ubuntu-zsh_arm64_2023-11-28_00-22-rootfs.tar.zst"
previous_sha256 = "7f2949eb921cf83e67f48fb11e63cd2f9ae4e66329c015e343ee50cb445e8be5"

current_version = "latest02"
current_date = "20240227"
old_file = "ubuntu-zsh_arm64_2023-11-21_00-23-rootfs.tar.zst"
old_sha256 = "56743afceb8f982f3803799f3288eea5afaeeffff805897dd5aa438f4da35d9c"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-zsh_arm64_2024-02-27_00-43-rootfs.tar.zst
# SHA256SUM=ed39b927b914f5d07b8a52d2be41d9d095d91dc39b5e339aba2f5086bd033001
# BUILD_DATE=20240227
# BUILD_TAG=2024-02-27
# STATUS=completed
# VERSION=latest02
# END_TIME=00:43

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-27
begin = 2024-02-27 00:02:33.507014217+00:00
start-sync_0 = 00:39:23
start-zstd = 00:40:57
start-sync_1 = 00:42:56
end-sync_1 = 00:43:07
end = 2024-02-27 00:43:07.337437782+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.39-0ubuntu2) 2.39'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
