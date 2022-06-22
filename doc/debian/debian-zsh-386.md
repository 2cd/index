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
tag = ["zsh", "2022-06-22"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_i386_2022-06-22_12-23.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "dca674dfc4131e49a1a7a8bd7a6f0702dcf0b09fe7dd7446d4462affbe0d6b97"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "759M"
tar_bytes = 795482624

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "151M"
zstd_bytes = 157768462

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220615"
previous_tag = "2022-06-15"
previous_file = "debian-zsh_i386_2022-06-15_12-18-rootfs.tar.zst"
previous_sha256 = "cb5b99b76ccb361110badfde99ce0c2ef0c2ad3f75515c88388b3aba479685c1"

current_version = "latest01"
current_date = "20220622"
old_file = "debian-zsh_i386_2022-06-08_12-19-rootfs.tar.zst"
old_sha256 = "2ad638394dd9f847f03db7368ca764344db906a085f117afcae78820284b168a"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-zsh_i386_2022-06-22_12-23-rootfs.tar.zst
# SHA256SUM=dca674dfc4131e49a1a7a8bd7a6f0702dcf0b09fe7dd7446d4462affbe0d6b97
# BUILD_DATE=20220622
# BUILD_TAG=2022-06-22
# STATUS=completed
# VERSION=latest01
# END_TIME=12:23

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-22
begin = 2022-06-22 12:02:31.456016121+00:00
start-sync_0 = 12:18:16
start-zstd = 12:20:11
start-sync_1 = 12:23:02
end-sync_1 = 12:23:19
end = 2022-06-22 12:23:19.796066006+00:00

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
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'
```
