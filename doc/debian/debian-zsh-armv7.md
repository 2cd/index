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
tag = ["zsh", "2022-06-08"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_armhf_2022-06-08_12-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d7d1ea51d48dfbc14a0278edbc4664eccabcc8337ab5ffc8763a0904e9c3e3d5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "679M"
tar_bytes = 710958080

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "141M"
zstd_bytes = 147092583

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220601"
previous_tag = "2022-06-01"
previous_file = "debian-zsh_armhf_2022-06-01_12-17-rootfs.tar.zst"
previous_sha256 = "943780659a44c1b4624ad7c1f656f28c80e98f56ef5269d2b3b5dde02b5ac314"

current_version = "latest01"
current_date = "20220608"
old_file = "debian-zsh_armhf_2022-05-25_12-21-rootfs.tar.zst"
old_sha256 = "7beea2af998778ce118883370460ba75d47775d327d7348cd4cf51c2f6bf0259"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-zsh_armhf_2022-06-08_12-17-rootfs.tar.zst
# SHA256SUM=d7d1ea51d48dfbc14a0278edbc4664eccabcc8337ab5ffc8763a0904e9c3e3d5
# BUILD_DATE=20220608
# BUILD_TAG=2022-06-08
# STATUS=completed
# VERSION=latest01
# END_TIME=12:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-08
begin = 2022-06-08 12:02:38.364980715+00:00
start-sync_0 = 12:13:45
start-zstd = 12:15:31
start-sync_1 = 12:17:40
end-sync_1 = 12:17:56
end = 2022-06-08 12:17:56.340467419+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```
