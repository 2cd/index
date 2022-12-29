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
tag = ["zsh", "2022-12-29"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2022-12-29_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "dcf216e00b172c53779aad7b1f0a633513f5a3f34ec3dcb342a1b9c85ac246b3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "758M"
tar_bytes = 794186240

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "147M"
zstd_bytes = 153892256

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221222"
previous_tag = "2022-12-22"
previous_file = "kali-zsh_amd64_2022-12-22_12-09-rootfs.tar.zst"
previous_sha256 = "75196a55b8719d7a6101528f66f7e7cf9f116c244c721b7156a7d22131095237"

current_version = "latest01"
current_date = "20221229"
old_file = "kali-zsh_amd64_2022-12-15_12-09-rootfs.tar.zst"
old_sha256 = "0d9690dcf1477e2bcc8c7997a884827c5088e363e41204eb7182087e358c96a1"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2022-12-29_12-09-rootfs.tar.zst
# SHA256SUM=dcf216e00b172c53779aad7b1f0a633513f5a3f34ec3dcb342a1b9c85ac246b3
# BUILD_DATE=20221229
# BUILD_TAG=2022-12-29
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-29
begin = 2022-12-29 12:02:32.109073389+00:00
start-sync_0 = 12:04:48
start-zstd = 12:06:41
start-sync_1 = 12:09:36
end-sync_1 = 12:09:51
end = 2022-12-29 12:09:51.336331557+00:00

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
