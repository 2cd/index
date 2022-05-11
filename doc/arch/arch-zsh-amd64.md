# arch-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-amd64 \
    cake233/arch-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it arch-zsh-amd64 zsh
```

## arch-zsh-amd64.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2022-05-11"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_amd64_2022-05-11_00-19.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5ec38905ad2573d1d6cd6df366669aa6b2edb5b704d54acb0a9a8b0894d47add"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "971M"
tar_bytes = 1017480704

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "254M"
zstd_bytes = 265761226

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220504"
previous_tag = "2022-05-04"
previous_file = "arch-zsh_amd64_2022-05-04_00-14-rootfs.tar.zst"
previous_sha256 = "ab5ac52937413a8c8884dd75a1dbf4644016a78f84f31c55839da2d0c0caecde"

current_version = "latest01"
current_date = "20220511"
old_file = "arch-zsh_amd64_2022-04-27_00-16-rootfs.tar.zst"
old_sha256 = "2d5e8fd452169f0e67b90144a2ee66e308fbbdea995aa3abb8a1e78caca2bcf3"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-zsh_amd64_2022-05-11_00-19-rootfs.tar.zst
# SHA256SUM=5ec38905ad2573d1d6cd6df366669aa6b2edb5b704d54acb0a9a8b0894d47add
# BUILD_DATE=20220511
# BUILD_TAG=2022-05-11
# STATUS=completed
# VERSION=latest01
# END_TIME=00:19

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-11
begin = 2022-05-11 00:12:26.524760493+00:00
start-sync_0 = 00:14:36
start-zstd = 00:16:04
start-sync_1 = 00:18:41
end-sync_1 = 00:19:04
end = 2022-05-11 00:19:04.924314090+00:00

[server]
repo = "cake233/arch-zsh-amd64"

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
zsh = 'zsh 5.8.1 (x86_64-pc-linux-gnu)'
```
