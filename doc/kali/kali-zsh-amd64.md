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
tag = ["zsh", "2023-06-08"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2023-06-08_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "33638322febd3325a9cf0305b58b743d4939b940c33d993b2bfc1d6ab1cc23e1"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "774M"
tar_bytes = 811466240

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "150M"
zstd_bytes = 156959309

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230601"
previous_tag = "2023-06-01"
previous_file = "kali-zsh_amd64_2023-06-01_12-10-rootfs.tar.zst"
previous_sha256 = "7d686c51fbe1449e6e181725c85e715c485977067d1df3f966745c3e3b8b6650"

current_version = "latest02"
current_date = "20230608"
old_file = "kali-zsh_amd64_2023-05-25_12-09-rootfs.tar.zst"
old_sha256 = "6e55a51eab617f93c2e9c99d68e49b0c3f7e5af1b34eb74e0a0b01e46d47ddbc"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2023-06-08_12-10-rootfs.tar.zst
# SHA256SUM=33638322febd3325a9cf0305b58b743d4939b940c33d993b2bfc1d6ab1cc23e1
# BUILD_DATE=20230608
# BUILD_TAG=2023-06-08
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-08
begin = 2023-06-08 12:02:35.359968348+00:00
start-sync_0 = 12:05:00
start-zstd = 12:06:52
start-sync_1 = 12:10:12
end-sync_1 = 12:10:29
end = 2023-06-08 12:10:29.648204754+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
