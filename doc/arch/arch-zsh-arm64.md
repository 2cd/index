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
tag = ["zsh", "2023-03-08"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_arm64_2023-03-08_00-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "78187fd85e58e1821bd05e833a22a91d128070b975e47dc24b5792cb9e45c3a3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1016M"
tar_bytes = 1065098240

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "238M"
zstd_bytes = 249379219

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230301"
previous_tag = "2023-03-01"
previous_file = "arch-zsh_arm64_2023-03-01_00-39-rootfs.tar.zst"
previous_sha256 = "b4cb11397c397445af9a47394f89536222818d461ef0a990222035900cb4a2bd"

current_version = "latest01"
current_date = "20230308"
old_file = "arch-zsh_arm64_2023-02-22_00-30-rootfs.tar.zst"
old_sha256 = "039faf1dd778aefb5780d73b3c1246c24e65ff1489ee92b7250897dc32bf814e"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2023-03-08_00-26-rootfs.tar.zst
# SHA256SUM=78187fd85e58e1821bd05e833a22a91d128070b975e47dc24b5792cb9e45c3a3
# BUILD_DATE=20230308
# BUILD_TAG=2023-03-08
# STATUS=completed
# VERSION=latest01
# END_TIME=00:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-08
begin = 2023-03-08 00:03:18.984832178+00:00
start-sync_0 = 00:20:28
start-zstd = 00:21:59
start-sync_1 = 00:25:45
end-sync_1 = 00:26:04
end = 2023-03-08 00:26:04.787550482+00:00

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
