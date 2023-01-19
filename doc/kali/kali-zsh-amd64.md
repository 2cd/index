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
tag = ["zsh", "2023-01-19"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2023-01-19_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "440a12e3c525b7bec264611fc3dc58d839367cb1b01d2db1fac56ae91d1df36e"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "764M"
tar_bytes = 800908800

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "147M"
zstd_bytes = 153612407

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230112"
previous_tag = "2023-01-12"
previous_file = "kali-zsh_amd64_2023-01-12_12-09-rootfs.tar.zst"
previous_sha256 = "734ba33823bfa609b5ac6600e23d84c2fd1a3e2e547990b2cbb0a63ef967f976"

current_version = "latest02"
current_date = "20230119"
old_file = "kali-zsh_amd64_2023-01-05_12-09-rootfs.tar.zst"
old_sha256 = "d06c385a6db32cb6e146cb7407ec187baf9c9c54a015ae5048f91be97a8a0f54"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2023-01-19_12-09-rootfs.tar.zst
# SHA256SUM=440a12e3c525b7bec264611fc3dc58d839367cb1b01d2db1fac56ae91d1df36e
# BUILD_DATE=20230119
# BUILD_TAG=2023-01-19
# STATUS=completed
# VERSION=latest02
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-19
begin = 2023-01-19 12:02:26.736852241+00:00
start-sync_0 = 12:04:44
start-zstd = 12:06:28
start-sync_1 = 12:09:20
end-sync_1 = 12:09:33
end = 2023-01-19 12:09:33.367008868+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-6) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
