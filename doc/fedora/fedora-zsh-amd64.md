# fedora-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name fedora-zsh-amd64 \
    cake233/fedora-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it fedora-zsh-amd64 zsh
```

## fedora-zsh-amd64.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2023-06-13"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_amd64_2023-06-13_12-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f77ec967af1cd5e3be6fd2ba5e6646d3cfb3ed7d0caf8341ad6a4324e424c7d2"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1371230720

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "229M"
zstd_bytes = 240070225

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230530"
previous_tag = "2023-05-30"
previous_file = "fedora-zsh_amd64_2023-05-30_12-11-rootfs.tar.zst"
previous_sha256 = "fd6e76441f8dd1b6231328dc7ccdf410b310a117bb8526cc30c1042ed5269fd7"

current_version = "latest01"
current_date = "20230613"
old_file = "fedora-zsh_amd64_2023-05-23_12-11-rootfs.tar.zst"
old_sha256 = "7d839fc4ec87899f4b5022e2ef59a79b763734d92c8068ebee97ffcd72ba14b7"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2023-06-13_12-13-rootfs.tar.zst
# SHA256SUM=f77ec967af1cd5e3be6fd2ba5e6646d3cfb3ed7d0caf8341ad6a4324e424c7d2
# BUILD_DATE=20230613
# BUILD_TAG=2023-06-13
# STATUS=completed
# VERSION=latest01
# END_TIME=12:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-13
begin = 2023-06-13 12:02:32.416328408+00:00
start-sync_0 = 12:05:21
start-zstd = 12:07:41
start-sync_1 = 12:12:57
end-sync_1 = 12:13:23
end = 2023-06-13 12:13:23.744249161+00:00

[server]
repo = "cake233/fedora-zsh-amd64"

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
ldd = 'ldd (GNU libc) 2.37.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'
```
