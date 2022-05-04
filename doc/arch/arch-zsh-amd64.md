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
tag = ["zsh", "2022-05-04"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_amd64_2022-05-04_00-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fb9d2ad275274306d833ab26aa9d65996c4b0e711ac9b4373f9bd470b54111ab"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "957M"
tar_bytes = 1002736640

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "254M"
zstd_bytes = 265730367

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220427"
previous_tag = "2022-04-27"
previous_file = "arch-zsh_amd64_2022-04-27_00-16-rootfs.tar.zst"
previous_sha256 = "2d5e8fd452169f0e67b90144a2ee66e308fbbdea995aa3abb8a1e78caca2bcf3"

current_version = "latest02"
current_date = "20220504"
old_file = "arch-zsh_amd64_2022-04-20_00-11-rootfs.tar.zst"
old_sha256 = "f9ef8cbcb196262d74378521b080a5ebaa340034f60234b152eaf4040d7637dd"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-zsh_amd64_2022-05-04_00-14-rootfs.tar.zst
# SHA256SUM=fb9d2ad275274306d833ab26aa9d65996c4b0e711ac9b4373f9bd470b54111ab
# BUILD_DATE=20220504
# BUILD_TAG=2022-05-04
# STATUS=completed
# VERSION=latest02
# END_TIME=00:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-04
begin = 2022-05-04 00:08:21.084683621+00:00
start-sync_0 = 00:10:07
start-zstd = 00:11:34
start-sync_1 = 00:13:56
end-sync_1 = 00:14:15
end = 2022-05-04 00:14:15.209684610+00:00

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
