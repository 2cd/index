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
tag = ["zsh", "2024-02-08"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2024-02-08_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c7f84544882ae0cfb0d2302d5517ccdfececbfbd9a775ea08d37ea0937b47b52"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "749M"
tar_bytes = 784456704

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "146M"
zstd_bytes = 152889488

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231123"
previous_tag = "2023-11-23"
previous_file = "kali-zsh_amd64_2023-11-23_12-08-rootfs.tar.zst"
previous_sha256 = "49bd5b112a5355b9eacfecfbc04f4eda89eaf98a8445a0d500116ae927b2a4d4"

current_version = "latest01"
current_date = "20240208"
old_file = "kali-zsh_amd64_2023-11-16_12-08-rootfs.tar.zst"
old_sha256 = "00a8cb4233616488af98b82bf3d385faba3681c3076f7597a75965b97497ef6a"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2024-02-08_12-08-rootfs.tar.zst
# SHA256SUM=c7f84544882ae0cfb0d2302d5517ccdfececbfbd9a775ea08d37ea0937b47b52
# BUILD_DATE=20240208
# BUILD_TAG=2024-02-08
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-08
begin = 2024-02-08 12:02:30.926860609+00:00
start-sync_0 = 12:04:10
start-zstd = 12:05:52
start-sync_1 = 12:08:17
end-sync_1 = 12:08:31
end = 2024-02-08 12:08:31.291270430+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
