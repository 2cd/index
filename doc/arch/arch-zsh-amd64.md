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
tag = ["zsh", "2023-09-13"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_amd64_2023-09-13_00-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c0855df6f9f97a5b1153e4613307a4cf89c8ddb5afd82669a34e20b168c303bf"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1162101248

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "278M"
zstd_bytes = 291179211

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230906"
previous_tag = "2023-09-06"
previous_file = "arch-zsh_amd64_2023-09-06_00-18-rootfs.tar.zst"
previous_sha256 = "5b0c0601130fb7801eaa889a785ea1247288b32ce510ac4a0ebdc54301422447"

current_version = "latest01"
current_date = "20230913"
old_file = "arch-zsh_amd64_2023-08-30_00-21-rootfs.tar.zst"
old_sha256 = "f19956b9b48d57044e9b7127fbfd3281b6926a03dcc693a70bfd0a68927d0613"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-zsh_amd64_2023-09-13_00-26-rootfs.tar.zst
# SHA256SUM=c0855df6f9f97a5b1153e4613307a4cf89c8ddb5afd82669a34e20b168c303bf
# BUILD_DATE=20230913
# BUILD_TAG=2023-09-13
# STATUS=completed
# VERSION=latest01
# END_TIME=00:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-13
begin = 2023-09-13 00:16:22.571666902+00:00
start-sync_0 = 00:20:29
start-zstd = 00:21:59
start-sync_1 = 00:25:32
end-sync_1 = 00:26:00
end = 2023-09-13 00:26:00.621523553+00:00

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
ldd = 'ldd (GNU libc) 2.38'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
