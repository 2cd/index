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
tag = ["zsh", "2023-02-09"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_armhf_2023-02-09_12-24.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2f1e8af6751d65f96b7c47c4f801a847e271de1ef0150b70d26d86bc7c15a362"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "758M"
tar_bytes = 794621952

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "143M"
zstd_bytes = 149135143

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230202"
previous_tag = "2023-02-02"
previous_file = "kali-zsh_armhf_2023-02-02_12-27-rootfs.tar.zst"
previous_sha256 = "7ec441645121d1182321abb03bc50f03a3167cec8f6f24321b1893b94ae3548d"

current_version = "latest01"
current_date = "20230209"
old_file = "kali-zsh_armhf_2023-01-26_12-24-rootfs.tar.zst"
old_sha256 = "617e20744c467454da3fda3b55acf25c87843e127d3c66ddd7293ff4228170ea"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2023-02-09_12-24-rootfs.tar.zst
# SHA256SUM=2f1e8af6751d65f96b7c47c4f801a847e271de1ef0150b70d26d86bc7c15a362
# BUILD_DATE=20230209
# BUILD_TAG=2023-02-09
# STATUS=completed
# VERSION=latest01
# END_TIME=12:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-09
begin = 2023-02-09 12:02:26.889440301+00:00
start-sync_0 = 12:20:05
start-zstd = 12:21:53
start-sync_1 = 12:24:10
end-sync_1 = 12:24:26
end = 2023-02-09 12:24:26.171745026+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabi)'
```
