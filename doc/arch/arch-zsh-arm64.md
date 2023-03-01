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
tag = ["zsh", "2023-03-01"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_arm64_2023-03-01_00-39.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b4cb11397c397445af9a47394f89536222818d461ef0a990222035900cb4a2bd"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1016M"
tar_bytes = 1065056256

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "238M"
zstd_bytes = 249402880

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230222"
previous_tag = "2023-02-22"
previous_file = "arch-zsh_arm64_2023-02-22_00-30-rootfs.tar.zst"
previous_sha256 = "039faf1dd778aefb5780d73b3c1246c24e65ff1489ee92b7250897dc32bf814e"

current_version = "latest02"
current_date = "20230301"
old_file = "arch-zsh_arm64_2023-02-15_00-31-rootfs.tar.zst"
old_sha256 = "364363938107c26b491a8056dba5671c0904ab7f4f2c7a42ade6fb3774e8ae0b"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2023-03-01_00-39-rootfs.tar.zst
# SHA256SUM=b4cb11397c397445af9a47394f89536222818d461ef0a990222035900cb4a2bd
# BUILD_DATE=20230301
# BUILD_TAG=2023-03-01
# STATUS=completed
# VERSION=latest02
# END_TIME=00:39

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-01
begin = 2023-03-01 00:09:03.690314631+00:00
start-sync_0 = 00:33:33
start-zstd = 00:35:08
start-sync_1 = 00:39:19
end-sync_1 = 00:39:44
end = 2023-03-01 00:39:44.292254149+00:00

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
