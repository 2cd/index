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
tag = ["zsh", "2022-05-05"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_armhf_2022-05-05_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d9f990e46eebe92671c42bacf58b858dd08d260da0e3788d3a48d594871fc019"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "675M"
tar_bytes = 707461120

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "139M"
zstd_bytes = 145220529

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220428"
previous_tag = "2022-04-28"
previous_file = "kali-zsh_armhf_2022-04-28_12-17-rootfs.tar.zst"
previous_sha256 = "7a21d9457a688ecd9ce2e08fbe1c60931444a3a6b7454ad5dc6a8c096a1c00b0"

current_version = "latest02"
current_date = "20220505"
old_file = "kali-zsh_armhf_2022-04-21_12-17-rootfs.tar.zst"
old_sha256 = "e1c640c1688fbb3660c8ce609c1f624e19d5be93289e7e05d8fd35bf36e10b6d"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2022-05-05_12-18-rootfs.tar.zst
# SHA256SUM=d9f990e46eebe92671c42bacf58b858dd08d260da0e3788d3a48d594871fc019
# BUILD_DATE=20220505
# BUILD_TAG=2022-05-05
# STATUS=completed
# VERSION=latest02
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-05
begin = 2022-05-05 12:02:33.485372939+00:00
start-sync_0 = 12:14:06
start-zstd = 12:15:52
start-sync_1 = 12:18:17
end-sync_1 = 12:18:35
end = 2022-05-05 12:18:35.833576919+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.8.1 (arm-unknown-linux-gnueabihf)'
```
