# debian-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-armv7 \
    cake233/debian-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it debian-zsh-armv7 zsh
```

## debian-zsh-armv7.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2022-03-23"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "debian-zsh_armhf_2022-03-23_12-17.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "13f76e782b3100b482bde73d8d5c1a62b33bb7b659d452a32689972304f144a5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "672M"
tar_bytes = 703780352

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "138M"
zstd_bytes = 144244279

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220316"
previous_tag = "2022-03-16"
previous_file = "debian-zsh_armhf_2022-03-16_12-17-rootfs.tar.zst"
previous_sha256 = "92de2466c146bd3ca2214bb97a546e731c19fcea5cfe678ae09e3a435d6fab9d"

current_version = "latest02"
current_date = "20220323"
old_file = "debian-zsh_armhf_2022-03-09_12-17-rootfs.tar.zst"
old_sha256 = "d398a0d72ca5b47e3c45dd61219fd318c2a7318d6a1a9e62b206ec8bd67dc387"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-zsh_armhf_2022-03-23_12-17-rootfs.tar.zst
# SHA256SUM=13f76e782b3100b482bde73d8d5c1a62b33bb7b659d452a32689972304f144a5
# BUILD_DATE=20220323
# BUILD_TAG=2022-03-23
# STATUS=completed
# VERSION=latest02
# END_TIME=12:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-23
begin = 2022-03-23 12:02:36.314348763+00:00
start-sync_0 = 12:13:35
start-zstd = 12:15:23
start-sync_1 = 12:17:35
end-sync_1 = 12:17:52
end = 2022-03-23 12:17:52.168166999+00:00

[server]
repo = "cake233/debian-zsh-armv7"

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.8.1 (arm-unknown-linux-gnueabihf)'
```
