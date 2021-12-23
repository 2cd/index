# kali-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-armv7 \
    cake233/kali-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it kali-zsh-armv7 zsh
```

## kali-zsh-armv7.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2021-12-23"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "kali-zsh_armhf_2021-12-23_12-19.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "4299a7f82e2084685b10efdd20febd3dd4447a13ce4984b1e01aad11cc7e6221"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "660M"
tar_bytes = 691562496

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "136M"
zstd_bytes = 141677316

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211216"
previous_tag = "2021-12-16"
previous_file = "kali-zsh_armhf_2021-12-16_12-20-rootfs.tar.zst"
previous_sha256 = "b1d45e76a85d2724b4356655691a535427cba314178e3c7cd3e21c900ee98605"

current_version = "latest01"
current_date = "20211223"
old_file = "kali-zsh_armhf_2021-12-09_12-19-rootfs.tar.zst"
old_sha256 = "d52c19328aa43b1153609597e8dc7e56cf95bb51ccfa49f5d019e311bf7d1aab"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2021-12-23_12-19-rootfs.tar.zst
# SHA256SUM=4299a7f82e2084685b10efdd20febd3dd4447a13ce4984b1e01aad11cc7e6221
# BUILD_DATE=20211223
# BUILD_TAG=2021-12-23
# STATUS=completed
# VERSION=latest01
# END_TIME=12:19

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-23
begin = 2021-12-23 12:02:25.232432008+00:00
start-sync_0 = 12:15:07
start-zstd = 12:16:49
start-sync_1 = 12:18:55
end-sync_1 = 12:19:13
end = 2021-12-23 12:19:13.370882133+00:00

[server]
repo = "cake233/kali-zsh-armv7"

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
zsh = 'zsh 5.8 (arm-unknown-linux-gnueabihf)'
```
