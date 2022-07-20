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
tag = ["zsh", "2022-07-20"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_i386_2022-07-20_12-22.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a61c70e0c38a550c7ed77d487b4d32b7bf1b237a40ad002a09314f8398572116"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "760M"
tar_bytes = 796212736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "151M"
zstd_bytes = 157790307

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220713"
previous_tag = "2022-07-13"
previous_file = "debian-zsh_i386_2022-07-13_12-17-rootfs.tar.zst"
previous_sha256 = "0b1b8a7f7a6e8cdb6eafcb96f1dc2e009e11f86db885c58462d3e8b2a21bbf48"

current_version = "latest01"
current_date = "20220720"
old_file = "debian-zsh_i386_2022-07-06_12-19-rootfs.tar.zst"
old_sha256 = "becca8bef7c9da9ddb92c9faa2f27addb4a9c5b7eb18d42886f0f5a66e571bc2"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-zsh_i386_2022-07-20_12-22-rootfs.tar.zst
# SHA256SUM=a61c70e0c38a550c7ed77d487b4d32b7bf1b237a40ad002a09314f8398572116
# BUILD_DATE=20220720
# BUILD_TAG=2022-07-20
# STATUS=completed
# VERSION=latest01
# END_TIME=12:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-20
begin = 2022-07-20 12:02:28.665423692+00:00
start-sync_0 = 12:17:14
start-zstd = 12:19:02
start-sync_1 = 12:22:14
end-sync_1 = 12:22:31
end = 2022-07-20 12:22:31.724019864+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-8) 2.33'
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'
```
