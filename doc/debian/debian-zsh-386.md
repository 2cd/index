# debian-zsh-386

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-386 \
    cake233/debian-zsh-386
```

## How to exec shell?

```sh
docker exec -it debian-zsh-386 zsh
```

## debian-zsh-386.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2022-05-04"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_i386_2022-05-04_14-21.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c7c0080c16f6767044dbca7d9b141b941ef50c4c216a9ffda3d895e699d97187"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "752M"
tar_bytes = 788040704

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "148M"
zstd_bytes = 154712815

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220427"
previous_tag = "2022-04-27"
previous_file = "debian-zsh_i386_2022-04-27_12-18-rootfs.tar.zst"
previous_sha256 = "ef89be28465ff52f5af3d5280b69a509961ff85cefa0b4c01d21dff6337eceb0"

current_version = "latest02"
current_date = "20220504"
old_file = "debian-zsh_i386_2022-04-20_12-20-rootfs.tar.zst"
old_sha256 = "897d711e8cb1920d31bbd2c5dabac4571a6e2b900e30274fb2dd54e62543dd28"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-zsh_i386_2022-05-04_14-21-rootfs.tar.zst
# SHA256SUM=c7c0080c16f6767044dbca7d9b141b941ef50c4c216a9ffda3d895e699d97187
# BUILD_DATE=20220504
# BUILD_TAG=2022-05-04
# STATUS=completed
# VERSION=latest02
# END_TIME=14:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-04
begin = 2022-05-04 14:05:56.622331895+00:00
start-sync_0 = 14:17:22
start-zstd = 14:19:06
start-sync_1 = 14:21:23
end-sync_1 = 14:21:38
end = 2022-05-04 14:21:38.195646673+00:00

[server]
repo = "cake233/debian-zsh-386"

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.8.1 (i686-debian-linux-gnu)'
```
