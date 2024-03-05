# fedora-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name fedora-zsh-arm64 \
    cake233/fedora-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it fedora-zsh-arm64 zsh
```

## fedora-zsh-arm64.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2024-03-05"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_arm64_2024-03-05_12-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b0a199ba4b156ea797ddbae8da762e03584d0791fe37734348023f753096e3a0"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1512824320

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "218M"
zstd_bytes = 228504228

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231121"
previous_tag = "2023-11-21"
previous_file = "fedora-zsh_arm64_2023-11-21_12-39-rootfs.tar.zst"
previous_sha256 = "0556161d949de5a766ce1bdf709f9cade15fdcc3e710eea70b5f647ed0239af4"

current_version = "latest01"
current_date = "20240305"
old_file = "fedora-zsh_arm64_2023-11-14_12-59-rootfs.tar.zst"
old_sha256 = "1fe588216e9d7b5abac29502c43ff6f1b6817fb2477a9e55f8a25f1512a1fb1f"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2024-03-05_12-28-rootfs.tar.zst
# SHA256SUM=b0a199ba4b156ea797ddbae8da762e03584d0791fe37734348023f753096e3a0
# BUILD_DATE=20240305
# BUILD_TAG=2024-03-05
# STATUS=completed
# VERSION=latest01
# END_TIME=12:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-03-05
begin = 2024-03-05 12:02:29.364994471+00:00
start-sync_0 = 12:22:39
start-zstd = 12:24:23
start-sync_1 = 12:27:46
end-sync_1 = 12:28:00
end = 2024-03-05 12:28:00.385584671+00:00

[server]
repo = "cake233/fedora-zsh-arm64"

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
ldd = 'ldd (GNU libc) 2.39.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'
```
