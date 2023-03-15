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
tag = ["zsh", "2023-03-15"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_i386_2023-03-15_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0dc2b9f2145432dc18ba56ebaa6acf474696b6caee67a2b3ee738ce4082e10ab"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "777M"
tar_bytes = 814713856

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "154M"
zstd_bytes = 160891457

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230308"
previous_tag = "2023-03-08"
previous_file = "debian-zsh_i386_2023-03-08_12-21-rootfs.tar.zst"
previous_sha256 = "b864b90d1973b5e53e9ed4a84739f853e5552195ff510674245004858de1db26"

current_version = "latest02"
current_date = "20230315"
old_file = "debian-zsh_i386_2023-03-01_12-18-rootfs.tar.zst"
old_sha256 = "7247f9d05489abe30cce1b32e0d9e5ef4ec91600084ea7f210c0a0234724b4c3"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-zsh_i386_2023-03-15_12-18-rootfs.tar.zst
# SHA256SUM=0dc2b9f2145432dc18ba56ebaa6acf474696b6caee67a2b3ee738ce4082e10ab
# BUILD_DATE=20230315
# BUILD_TAG=2023-03-15
# STATUS=completed
# VERSION=latest02
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-15
begin = 2023-03-15 12:02:30.617875075+00:00
start-sync_0 = 12:13:53
start-zstd = 12:15:44
start-sync_1 = 12:18:22
end-sync_1 = 12:18:35
end = 2023-03-15 12:18:35.668864407+00:00

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
