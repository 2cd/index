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
tag = ["zsh", "2023-08-24"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_armhf_2023-08-24_12-30.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9892db47566c2f24045b00d58ff06d49e9d8c68911a2bf801c5ee0ca7dfb202a"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "779M"
tar_bytes = 816547328

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "156M"
zstd_bytes = 163420161

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230817"
previous_tag = "2023-08-17"
previous_file = "kali-zsh_armhf_2023-08-17_12-26-rootfs.tar.zst"
previous_sha256 = "5f4131d62e64f325788e230dff377fde3ced511af6eb6b22a7d6a4470dc02be1"

current_version = "latest01"
current_date = "20230824"
old_file = "kali-zsh_armhf_2023-08-10_12-29-rootfs.tar.zst"
old_sha256 = "d2194739bf7dda20173bfb062d5e430b307f48b9057c2d2d6d758d58ba9e315b"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2023-08-24_12-30-rootfs.tar.zst
# SHA256SUM=9892db47566c2f24045b00d58ff06d49e9d8c68911a2bf801c5ee0ca7dfb202a
# BUILD_DATE=20230824
# BUILD_TAG=2023-08-24
# STATUS=completed
# VERSION=latest01
# END_TIME=12:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-24
begin = 2023-08-24 12:02:37.155569145+00:00
start-sync_0 = 12:24:44
start-zstd = 12:26:31
start-sync_1 = 12:29:52
end-sync_1 = 12:30:13
end = 2023-08-24 12:30:13.062029820+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-6) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabi)'
```
