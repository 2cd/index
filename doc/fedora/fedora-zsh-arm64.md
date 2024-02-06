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
tag = ["zsh", "2024-02-06"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_arm64_2024-02-06_12-45.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0341ea62958d0a682c93cb9b21e21b0e2b66e9746f54df8030279ea16377b63c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1520678400

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "219M"
zstd_bytes = 228745467

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231121"
previous_tag = "2023-11-21"
previous_file = "fedora-zsh_arm64_2023-11-21_12-39-rootfs.tar.zst"
previous_sha256 = "0556161d949de5a766ce1bdf709f9cade15fdcc3e710eea70b5f647ed0239af4"

current_version = "latest01"
current_date = "20240206"
old_file = "fedora-zsh_arm64_2023-11-14_12-59-rootfs.tar.zst"
old_sha256 = "1fe588216e9d7b5abac29502c43ff6f1b6817fb2477a9e55f8a25f1512a1fb1f"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2024-02-06_12-45-rootfs.tar.zst
# SHA256SUM=0341ea62958d0a682c93cb9b21e21b0e2b66e9746f54df8030279ea16377b63c
# BUILD_DATE=20240206
# BUILD_TAG=2024-02-06
# STATUS=completed
# VERSION=latest01
# END_TIME=12:45

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-06
begin = 2024-02-06 12:02:34.482304071+00:00
start-sync_0 = 12:39:50
start-zstd = 12:41:35
start-sync_1 = 12:44:48
end-sync_1 = 12:45:03
end = 2024-02-06 12:45:03.224208600+00:00

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
ldd = 'ldd (GNU libc) 2.38.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'
```
