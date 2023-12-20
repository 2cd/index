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
tag = ["zsh", "2023-12-20"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_amd64_2023-12-20_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6794dbeeab3dd73970bac237cba763b0614f57de9848b67289bbe8df4dd0f5f4"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "784M"
tar_bytes = 821499392

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "152M"
zstd_bytes = 159347596

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-zsh_amd64_2023-11-22_12-08-rootfs.tar.zst"
previous_sha256 = "004cb4a492bb75e51a4ab9e8e2510407b07c288953494240c70b97399ccf0bc1"

current_version = "latest01"
current_date = "20231220"
old_file = "debian-zsh_amd64_2023-11-15_12-08-rootfs.tar.zst"
old_sha256 = "151c473a389fbc2ecae2f7d746c0c8433fed817b4eb25ba2ce195a785edb8732"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-zsh_amd64_2023-12-20_12-08-rootfs.tar.zst
# SHA256SUM=6794dbeeab3dd73970bac237cba763b0614f57de9848b67289bbe8df4dd0f5f4
# BUILD_DATE=20231220
# BUILD_TAG=2023-12-20
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-20
begin = 2023-12-20 12:02:33.161710691+00:00
start-sync_0 = 12:04:15
start-zstd = 12:05:58
start-sync_1 = 12:08:33
end-sync_1 = 12:08:45
end = 2023-12-20 12:08:45.396911396+00:00

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
