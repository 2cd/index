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
tag = ["zsh", "2023-09-21"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2023-09-21_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d1074a18e4a865f8fa4a25e8eb6f6180e1f132a2ecec0769a35fa78f803ff4db"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "817M"
tar_bytes = 856129536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "163M"
zstd_bytes = 170008908

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230914"
previous_tag = "2023-09-14"
previous_file = "kali-zsh_amd64_2023-09-14_12-10-rootfs.tar.zst"
previous_sha256 = "5ebec198f7f838d277ab6678899487c511c94ff60ae9c7f32e000e1e9c951f7e"

current_version = "latest02"
current_date = "20230921"
old_file = "kali-zsh_amd64_2023-09-07_12-09-rootfs.tar.zst"
old_sha256 = "1220b3a404a818dbb5f880a7e735d0fb7f3844269cd7b68e5ad153a85e9de462"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2023-09-21_12-09-rootfs.tar.zst
# SHA256SUM=d1074a18e4a865f8fa4a25e8eb6f6180e1f132a2ecec0769a35fa78f803ff4db
# BUILD_DATE=20230921
# BUILD_TAG=2023-09-21
# STATUS=completed
# VERSION=latest02
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-21
begin = 2023-09-21 12:02:35.961759468+00:00
start-sync_0 = 12:04:52
start-zstd = 12:06:35
start-sync_1 = 12:09:32
end-sync_1 = 12:09:48
end = 2023-09-21 12:09:48.154784729+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
