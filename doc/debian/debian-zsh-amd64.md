# debian-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-amd64 \
    cake233/debian-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it debian-zsh-amd64 zsh
```

## debian-zsh-amd64.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2024-01-17"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_amd64_2024-01-17_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "469e787e9d295f247d7f97fb3d158c4dc8535374d603e0e392eee9bd5ae3029c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "787M"
tar_bytes = 825014272

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "155M"
zstd_bytes = 162110786

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-zsh_amd64_2023-11-22_12-08-rootfs.tar.zst"
previous_sha256 = "004cb4a492bb75e51a4ab9e8e2510407b07c288953494240c70b97399ccf0bc1"

current_version = "latest01"
current_date = "20240117"
old_file = "debian-zsh_amd64_2023-11-15_12-08-rootfs.tar.zst"
old_sha256 = "151c473a389fbc2ecae2f7d746c0c8433fed817b4eb25ba2ce195a785edb8732"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-zsh_amd64_2024-01-17_12-09-rootfs.tar.zst
# SHA256SUM=469e787e9d295f247d7f97fb3d158c4dc8535374d603e0e392eee9bd5ae3029c
# BUILD_DATE=20240117
# BUILD_TAG=2024-01-17
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-17
begin = 2024-01-17 12:02:31.907785348+00:00
start-sync_0 = 12:04:28
start-zstd = 12:06:13
start-sync_1 = 12:08:53
end-sync_1 = 12:09:05
end = 2024-01-17 12:09:05.994394293+00:00

[server]
repo = "cake233/debian-zsh-amd64"

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
ldd = 'ldd (Debian GLIBC 2.37-13) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
