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
tag = ["zsh", "2022-09-14"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_arm64_2022-09-14_00-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "071d01a0acd038319ac22e6c598249863ac9c39e3328ef4cff952034b2733fc3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "966M"
tar_bytes = 1012579840

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "228M"
zstd_bytes = 238602005

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220907"
previous_tag = "2022-09-07"
previous_file = "arch-zsh_arm64_2022-09-07_00-28-rootfs.tar.zst"
previous_sha256 = "bb3503bf789c6e242132f1237b92f9689a95fbaca65e65dc30949f84e32c71f6"

current_version = "latest02"
current_date = "20220914"
old_file = "arch-zsh_arm64_2022-08-31_00-46-rootfs.tar.zst"
old_sha256 = "d5dfc4dc13a645f1749f45d5be40f927db6f85f98d7eee346609a3224478858b"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2022-09-14_00-28-rootfs.tar.zst
# SHA256SUM=071d01a0acd038319ac22e6c598249863ac9c39e3328ef4cff952034b2733fc3
# BUILD_DATE=20220914
# BUILD_TAG=2022-09-14
# STATUS=completed
# VERSION=latest02
# END_TIME=00:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-14
begin = 2022-09-14 00:08:08.602412331+00:00
start-sync_0 = 00:23:05
start-zstd = 00:24:36
start-sync_1 = 00:28:04
end-sync_1 = 00:28:26
end = 2022-09-14 00:28:26.590984668+00:00

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
