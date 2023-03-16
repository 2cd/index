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
tag = ["zsh", "2023-03-16"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2023-03-16_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8b24dbf9eb6d1a379227eabe5ddde552ecd309233b75538764fab25096eac419"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "774M"
tar_bytes = 810807808

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "150M"
zstd_bytes = 156942295

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230309"
previous_tag = "2023-03-09"
previous_file = "kali-zsh_amd64_2023-03-09_12-09-rootfs.tar.zst"
previous_sha256 = "e763013147046c1048560411078bfe6b8b1d870cac6d7ccd3f7035bc801423b5"

current_version = "latest02"
current_date = "20230316"
old_file = "kali-zsh_amd64_2023-03-02_12-10-rootfs.tar.zst"
old_sha256 = "7fab6c88d0dae6a4ed49406ccbb134789ab764ea099a93bc6baf788678d62e14"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2023-03-16_12-09-rootfs.tar.zst
# SHA256SUM=8b24dbf9eb6d1a379227eabe5ddde552ecd309233b75538764fab25096eac419
# BUILD_DATE=20230316
# BUILD_TAG=2023-03-16
# STATUS=completed
# VERSION=latest02
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-16
begin = 2023-03-16 12:02:29.124392093+00:00
start-sync_0 = 12:04:24
start-zstd = 12:06:12
start-sync_1 = 12:09:11
end-sync_1 = 12:09:25
end = 2023-03-16 12:09:25.028021722+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
