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
tag = ["zsh", "2022-03-23"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
x11_or_wayland = false

[file]
name = "debian-zsh_i386_2022-03-23_12-22.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "805bd72df43cf10c0280ea61493a712dbddad8f9d5c4b5612a291ff4da9dfbfb"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "748M"
tar_bytes = 783475200

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "147M"
zstd_bytes = 153404819

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220316"
previous_tag = "2022-03-16"
previous_file = "debian-zsh_i386_2022-03-16_12-22-rootfs.tar.zst"
previous_sha256 = "4a4dd10c8a07be533a6d62e04830a76de2731cb322dfdfcc7e48d47133b0f77a"

current_version = "latest02"
current_date = "20220323"
old_file = "debian-zsh_i386_2022-03-09_12-21-rootfs.tar.zst"
old_sha256 = "9808604e6ac8ff131e0c6e4cd78791bed6595852872de71207493c127b09a00e"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-zsh_i386_2022-03-23_12-22-rootfs.tar.zst
# SHA256SUM=805bd72df43cf10c0280ea61493a712dbddad8f9d5c4b5612a291ff4da9dfbfb
# BUILD_DATE=20220323
# BUILD_TAG=2022-03-23
# STATUS=completed
# VERSION=latest02
# END_TIME=12:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-23
begin = 2022-03-23 12:02:37.436591855+00:00
start-sync_0 = 12:17:45
start-zstd = 12:19:46
start-sync_1 = 12:22:27
end-sync_1 = 12:22:48
end = 2022-03-23 12:22:48.252474086+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.8.1 (i686-debian-linux-gnu)'
```
