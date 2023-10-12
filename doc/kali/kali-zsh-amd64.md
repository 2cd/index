# kali-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-amd64 \
    cake233/kali-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it kali-zsh-amd64 zsh
```

## kali-zsh-amd64.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2023-10-12"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2023-10-12_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "932be226cd4b9bd1c0f44ca853850e9c6f674f485824e17008375f931c684231"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "779M"
tar_bytes = 816671744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "152M"
zstd_bytes = 158336702

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231005"
previous_tag = "2023-10-05"
previous_file = "kali-zsh_amd64_2023-10-05_12-09-rootfs.tar.zst"
previous_sha256 = "96ec3f983823258b3121a2a59d6f5ef02fa4e42a0e974708b420f3f0e96ccea9"

current_version = "latest01"
current_date = "20231012"
old_file = "kali-zsh_amd64_2023-09-28_12-10-rootfs.tar.zst"
old_sha256 = "ce84caada0308dc01fce18bdf09be52270725b6ed8e234d500c044dba6f3e3cb"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2023-10-12_12-09-rootfs.tar.zst
# SHA256SUM=932be226cd4b9bd1c0f44ca853850e9c6f674f485824e17008375f931c684231
# BUILD_DATE=20231012
# BUILD_TAG=2023-10-12
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-12
begin = 2023-10-12 12:02:31.757747920+00:00
start-sync_0 = 12:04:49
start-zstd = 12:06:29
start-sync_1 = 12:09:24
end-sync_1 = 12:09:42
end = 2023-10-12 12:09:42.924035403+00:00

[server]
repo = "cake233/kali-zsh-amd64"

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
