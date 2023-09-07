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
tag = ["zsh", "2023-09-07"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_armhf_2023-09-07_12-24.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f9a4f333d043aed7a67fed494d4fcf8c547fc5dba0f000b45180b209a77484fe"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "781M"
tar_bytes = 818053120

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "157M"
zstd_bytes = 163858220

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230831"
previous_tag = "2023-08-31"
previous_file = "kali-zsh_armhf_2023-08-31_12-26-rootfs.tar.zst"
previous_sha256 = "0244b9a9075c1d83aed6a148f67d9e3b2e8b3594609817324def47410b14e2ab"

current_version = "latest01"
current_date = "20230907"
old_file = "kali-zsh_armhf_2023-08-24_12-30-rootfs.tar.zst"
old_sha256 = "9892db47566c2f24045b00d58ff06d49e9d8c68911a2bf801c5ee0ca7dfb202a"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2023-09-07_12-24-rootfs.tar.zst
# SHA256SUM=f9a4f333d043aed7a67fed494d4fcf8c547fc5dba0f000b45180b209a77484fe
# BUILD_DATE=20230907
# BUILD_TAG=2023-09-07
# STATUS=completed
# VERSION=latest01
# END_TIME=12:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-07
begin = 2023-09-07 12:02:32.756425535+00:00
start-sync_0 = 12:19:58
start-zstd = 12:21:40
start-sync_1 = 12:24:19
end-sync_1 = 12:24:35
end = 2023-09-07 12:24:35.267949837+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabi)'
```
