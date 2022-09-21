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
tag = ["zsh", "2022-09-21"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_amd64_2022-09-21_00-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ca7c5c908ec29fd79b29d94e1c60140ddf36193c0cd9f1ce42d90c2118cd6e87"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1018M"
tar_bytes = 1066416128

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "256M"
zstd_bytes = 268314957

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220914"
previous_tag = "2022-09-14"
previous_file = "arch-zsh_amd64_2022-09-14_00-16-rootfs.tar.zst"
previous_sha256 = "1eca6276b952550845f7b44c409a1446d15660fe28d04a1867045cefd08e2f2d"

current_version = "latest01"
current_date = "20220921"
old_file = "arch-zsh_amd64_2022-09-07_00-15-rootfs.tar.zst"
old_sha256 = "21e17cc8190bb03d09d4d25ed3028903cd0851ee7e8560187e02719bb2de971c"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-zsh_amd64_2022-09-21_00-16-rootfs.tar.zst
# SHA256SUM=ca7c5c908ec29fd79b29d94e1c60140ddf36193c0cd9f1ce42d90c2118cd6e87
# BUILD_DATE=20220921
# BUILD_TAG=2022-09-21
# STATUS=completed
# VERSION=latest01
# END_TIME=00:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-21
begin = 2022-09-21 00:07:42.660039781+00:00
start-sync_0 = 00:10:42
start-zstd = 00:12:13
start-sync_1 = 00:15:52
end-sync_1 = 00:16:15
end = 2022-09-21 00:16:15.309100755+00:00

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
ldd = 'ldd (GNU libc) 2.36'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
