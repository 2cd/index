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
tag = ["zsh", "2023-02-01"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_arm64_2023-02-01_00-30.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ddf11d86780a6b5abb45f4d0d84a8b244094496942a96896b5faea5b2cbc4841"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1013M"
tar_bytes = 1061540864

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "237M"
zstd_bytes = 247619759

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230125"
previous_tag = "2023-01-25"
previous_file = "arch-zsh_arm64_2023-01-25_00-26-rootfs.tar.zst"
previous_sha256 = "c3b32baf8efc1c363b290a6126c3bb090a2b0810b9480c3b3d2e458c860b6fce"

current_version = "latest02"
current_date = "20230201"
old_file = "arch-zsh_arm64_2023-01-18_00-27-rootfs.tar.zst"
old_sha256 = "8a185fb7b2e67facba7ab033abd26f1e6a30756be39ddc3646d48caee390ee43"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2023-02-01_00-30-rootfs.tar.zst
# SHA256SUM=ddf11d86780a6b5abb45f4d0d84a8b244094496942a96896b5faea5b2cbc4841
# BUILD_DATE=20230201
# BUILD_TAG=2023-02-01
# STATUS=completed
# VERSION=latest02
# END_TIME=00:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-01
begin = 2023-02-01 00:09:19.130051537+00:00
start-sync_0 = 00:24:53
start-zstd = 00:26:25
start-sync_1 = 00:30:33
end-sync_1 = 00:30:55
end = 2023-02-01 00:30:55.073845942+00:00

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
