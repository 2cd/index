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
tag = ["zsh", "2022-08-17"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_arm64_2022-08-17_00-37.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "71189b25e5f568abee16480a08be5a4288ace6d03816d1bdf3ad3d20cff86b54"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "958M"
tar_bytes = 1003764736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "226M"
zstd_bytes = 236558035

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220810"
previous_tag = "2022-08-10"
previous_file = "arch-zsh_arm64_2022-08-10_00-29-rootfs.tar.zst"
previous_sha256 = "5d65492a26098a2d84da29ede5ad9c02dd45d32a4c396ff0cb047bc3e1a89a16"

current_version = "latest02"
current_date = "20220817"
old_file = "arch-zsh_arm64_2022-07-13_00-37-rootfs.tar.zst"
old_sha256 = "aae1d184449dfa97d269ea3da092721b68577b1912658ce60930e84c49721da5"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2022-08-17_00-37-rootfs.tar.zst
# SHA256SUM=71189b25e5f568abee16480a08be5a4288ace6d03816d1bdf3ad3d20cff86b54
# BUILD_DATE=20220817
# BUILD_TAG=2022-08-17
# STATUS=completed
# VERSION=latest02
# END_TIME=00:37

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-17
begin = 2022-08-17 00:15:32.858904589+00:00
start-sync_0 = 00:31:58
start-zstd = 00:33:27
start-sync_1 = 00:37:34
end-sync_1 = 00:37:56
end = 2022-08-17 00:37:56.285967496+00:00

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
