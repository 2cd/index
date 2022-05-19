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
tag = ["zsh", "2022-05-19"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2022-05-19_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "22c84a4ce34d2000084eb04285e1055df84b1904a752904d48027464e961bf8e"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "748M"
tar_bytes = 783366656

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "145M"
zstd_bytes = 151893450

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220512"
previous_tag = "2022-05-12"
previous_file = "kali-zsh_amd64_2022-05-12_12-10-rootfs.tar.zst"
previous_sha256 = "722f30dba5ed234c929e084c9c0aa679cb60a672f493ef05c21eaed7380a46b0"

current_version = "latest02"
current_date = "20220519"
old_file = "kali-zsh_amd64_2022-05-05_12-10-rootfs.tar.zst"
old_sha256 = "74be8ec2a0c5e2284331b9f194f94d2b529b357cabf96931f442c906b86dcb51"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2022-05-19_12-09-rootfs.tar.zst
# SHA256SUM=22c84a4ce34d2000084eb04285e1055df84b1904a752904d48027464e961bf8e
# BUILD_DATE=20220519
# BUILD_TAG=2022-05-19
# STATUS=completed
# VERSION=latest02
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-19
begin = 2022-05-19 12:02:31.550995695+00:00
start-sync_0 = 12:04:24
start-zstd = 12:06:11
start-sync_1 = 12:08:45
end-sync_1 = 12:09:00
end = 2022-05-19 12:09:00.025857389+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.8.1 (x86_64-debian-linux-gnu)'
```
