# debian-zsh-386

## How to run it?

```shell
docker run \
    -it \
    --name debian-zsh-386 \
    cake233/debian-zsh-386
```

## How to exec shell?

```shell
    docker exec -it debian-zsh-386 zsh
```

## debian-zsh-386.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2021-12-15"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
x11_or_wayland = false

[file]
name = "debian-zsh_i386_2021-12-15_12-18.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "763fc53eeeecde5930cc3b4395b681ed37ba7252eb25fd42d5653d983aa9092f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "736M"
tar_bytes = 770953216

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "144M"
zstd_bytes = 150120611

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211208"
previous_tag = "2021-12-08"
previous_file = "debian-zsh_i386_2021-12-08_12-18-rootfs.tar.zst"
previous_sha256 = "98184692410cd03ff555990ad91b2f7adecdbf5f05db360ee77c9d6d705954cb"

current_version = "latest02"
current_date = "20211215"
old_file = "debian-zsh_i386_2021-12-01_12-17-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-zsh_i386_2021-12-15_12-18-rootfs.tar.zst
# SHA256SUM=763fc53eeeecde5930cc3b4395b681ed37ba7252eb25fd42d5653d983aa9092f
# BUILD_DATE=20211215
# BUILD_TAG=2021-12-15
# STATUS=completed
# VERSION=latest02
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-15
begin = 2021-12-15 12:02:26.994756570+00:00
start-sync_0 = 12:13:44
start-zstd = 12:15:33
start-sync_1 = 12:17:43
end-sync_1 = 12:18:00
end = 2021-12-15 12:18:00.228402822+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (Debian GLIBC 2.33-1) 2.33'
zsh = 'zsh 5.8 (i686-debian-linux-gnu)'
```
