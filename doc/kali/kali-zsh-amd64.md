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
tag = ["zsh", "2023-07-13"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2023-07-13_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6406ba03cf7e66073b1365671a70f135e7aee70b67c490d2aeadb8d56e3b1e2c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "774M"
tar_bytes = 811108352

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "151M"
zstd_bytes = 157307936

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230706"
previous_tag = "2023-07-06"
previous_file = "kali-zsh_amd64_2023-07-06_12-09-rootfs.tar.zst"
previous_sha256 = "21fb5cfb603eedddece2abb9ca5d962483a6c62903283d9430eb96b90891e795"

current_version = "latest02"
current_date = "20230713"
old_file = "kali-zsh_amd64_2023-06-29_12-09-rootfs.tar.zst"
old_sha256 = "b7095164affd58f63ee90fe7ce2d0a20093dca2befbe79223aa4ad93236a81ab"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2023-07-13_12-09-rootfs.tar.zst
# SHA256SUM=6406ba03cf7e66073b1365671a70f135e7aee70b67c490d2aeadb8d56e3b1e2c
# BUILD_DATE=20230713
# BUILD_TAG=2023-07-13
# STATUS=completed
# VERSION=latest02
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-13
begin = 2023-07-13 12:02:31.043274281+00:00
start-sync_0 = 12:04:32
start-zstd = 12:06:16
start-sync_1 = 12:09:06
end-sync_1 = 12:09:19
end = 2023-07-13 12:09:19.407883931+00:00

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
