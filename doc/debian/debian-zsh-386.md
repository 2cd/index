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
tag = ["zsh", "2023-03-01"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_i386_2023-03-01_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7247f9d05489abe30cce1b32e0d9e5ef4ec91600084ea7f210c0a0234724b4c3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "777M"
tar_bytes = 814495232

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "154M"
zstd_bytes = 160931201

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230222"
previous_tag = "2023-02-22"
previous_file = "debian-zsh_i386_2023-02-22_12-18-rootfs.tar.zst"
previous_sha256 = "2b874beafa60dc51634bdfbe8eeb6444b36dc6329d197936d136658da83c6e24"

current_version = "latest02"
current_date = "20230301"
old_file = "debian-zsh_i386_2023-02-15_12-26-rootfs.tar.zst"
old_sha256 = "369833d11f61102556c2833cd3948b169619879304c84d058fc0489a228bea02"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-zsh_i386_2023-03-01_12-18-rootfs.tar.zst
# SHA256SUM=7247f9d05489abe30cce1b32e0d9e5ef4ec91600084ea7f210c0a0234724b4c3
# BUILD_DATE=20230301
# BUILD_TAG=2023-03-01
# STATUS=completed
# VERSION=latest02
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-01
begin = 2023-03-01 12:02:28.339822829+00:00
start-sync_0 = 12:13:31
start-zstd = 12:15:18
start-sync_1 = 12:18:12
end-sync_1 = 12:18:29
end = 2023-03-01 12:18:29.966045789+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'
```
